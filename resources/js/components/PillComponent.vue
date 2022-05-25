<template>
    <div class="d-flex flex-column align-items-end">
        <div @click="showMenu()">
            <span id="msPill" class="badge rounded-pill text-bg-light d-flex justify-content-end align-items-center">
                <i class="fa-solid fa-bars"></i>
                <i class="fa-solid fa-circle-user"></i>
            </span>
        </div>

        <div v-show="value1" id="hidden-menu">
            <div class="d-flex justify-content-start flex-column align-items-evenly py-3">
                <a href="">
                    Registrati
                </a>
                <a href="">
                    Login
                </a>
                <span>

                </span>
                <a href="">
                    Diventa un host
                </a>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                value1: false
            }
        },
        methods: {
            showMenu() {
                this.value1 = !this.value1;
                if (this.value1 == true) {
                    document.getElementById("msPill").classList.add("ms-box-shadow");
                } else {
                    document.getElementById("msPill").classList.remove("ms-box-shadow");
                }
            }
        },
        mounted() {
            document.addEventListener('click', function handleClickOutsideMenu(event) {
                    let hiddenMenu = document.getElementById('hidden-menu');

                    if (!hiddenMenu.contains(event.target)) {
                        this.value1 = false;
                        console.log(this.value1);
                    }
                });
            }
        }
</script>

<style lang="scss" scoped>

    .ms-box-shadow {
        box-shadow: 4px 4px 4px rgba(0, 0, 0, 0.1);
    }

    span {
        border: 1px solid #C9C4BE;
        color: #717171;
        width: 80px;
        height: 44px;
        gap: 15px;
        cursor: pointer;
        
        .fa-bars {
            font-size: 16px;
        }

        .fa-circle-user {
            font-size: 30px;
        }
    }

    span:hover {
        box-shadow: 4px 4px 4px rgba(0, 0, 0, 0.1);
    }

    #hidden-menu {
        box-shadow: 4px 4px 4px rgba(0, 0, 0, 0.1);
        width: 200px;
        border-radius: 10px;
        position: fixed;
        top: 75px;
        background-color: white;

        a {
            padding-left: 20px;
        }

        span {
            border: 0;
            border-bottom: 1px solid #C9C4BE;
            height: 0px;
            width: 100%;
            margin: 6px 0px;
            cursor: default;
        }

        span:hover {
        box-shadow: none;
        }

        a:first-child {
            font-weight: bold;
        }
    }

    a {
        text-decoration: none;
        color: #717171;
    }

    a:hover {
        background-color:rgb(243, 243, 243);
    }

</style>