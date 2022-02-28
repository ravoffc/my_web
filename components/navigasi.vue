<template>
    <main>
        <head>
            <meta charset="UTF-8">
            <!--<title> Responsive Sidebar Menu  | CodingLab </title>-->
            <!-- Boxicons CDN Link -->
            <link href='https://unpkg.com/boxicons@2.0.7/css/boxicons.min.css' rel='stylesheet'>
            <meta name="viewport" content="width=device-width, initial-scale=1.0">
        </head>
        <body>
        <div class="sidebar">
            <div class="logo-details">
                <div class="logo_name">My web</div>
                <i class='bx bx-menu' id="btn" ></i>
            </div>
            <ul class="nav-list">
            <li>
                <NuxtLink to="/" class="text-white cd-md-3">
                <i class='bx bxs-widget'></i>
                <span class="links_name">Home</span>
                </NuxtLink>
                <span class="tooltip">Home</span>
            </li>
            <li>
                <NuxtLink to="/about" class="text-white cd-md-3">
                    <i class='bx bxs-error-circle' ></i>
                    <span class="links_name">About</span>
                </NuxtLink>
                <span class="tooltip">About</span>
            </li>
            <li>
                <NuxtLink to="/Project" class="text-white cd-md-3">
                    <i class='bx bxl-magento'></i>
                    <span class="links_name">Project</span>
                </NuxtLink>
                <span class="tooltip">Project</span>
            </li>
            <li>
                <NuxtLink to="/Project" class="text-white cd-md-3">
                    <i class='bx bx-code-alt'></i>
                    <span class="links_name">Code</span>
                </NuxtLink>
                <span class="tooltip">Code</span>
            </li>
            <li>
                <NuxtLink to="/Project" class="text-white cd-md-3">
                    <i class='bx bx-chat' ></i>
                    <span class="links_name">Contact Us</span>
                </NuxtLink>
                <span class="tooltip">Contact Us</span>
            </li>
            <li class="profile">
                <div class="profile-details">
                <!--<img src="profile.jpg" alt="profileImg">-->
                <div class="name_job">
                    <div class="name">Copyright by ravoffc</div>
                    <div class="job">Software Engginering</div>
                </div>
                </div>
                <i class='bx bxs-user-circle' id="log_out"></i>
            </li>
            </ul>
        </div>
        <section class="home-section">
            <div class="text">ravoffc</div>
            <button class="btn btn-dark" style="float: right; margin: 18px; padding: 6px;">
                <a href="https://wa.me/message/UKG47JSXMNROM1" style="color: white;">
                    Help 
                    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-question-circle" viewBox="0 0 16 16">
                        <path d="M8 15A7 7 0 1 1 8 1a7 7 0 0 1 0 14zm0 1A8 8 0 1 0 8 0a8 8 0 0 0 0 16z"/>
                        <path d="M5.255 5.786a.237.237 0 0 0 .241.247h.825c.138 0 .248-.113.266-.25.09-.656.54-1.134 1.342-1.134.686 0 1.314.343 1.314 1.168 0 .635-.374.927-.965 1.371-.673.489-1.206 1.06-1.168 1.987l.003.217a.25.25 0 0 0 .25.246h.811a.25.25 0 0 0 .25-.25v-.105c0-.718.273-.927 1.01-1.486.609-.463 1.244-.977 1.244-2.056 0-1.511-1.276-2.241-2.673-2.241-1.267 0-2.655.59-2.75 2.286zm1.557 5.763c0 .533.425.927 1.01.927.609 0 1.028-.394 1.028-.927 0-.552-.42-.94-1.029-.94-.584 0-1.009.388-1.009.94z"/>
                    </svg>
                </a>
            </button>
        </section>
        <script>
            let sidebar = document.querySelector(".sidebar");
            let closeBtn = document.querySelector("#btn");
            let searchBtn = document.querySelector(".bx-search");

            closeBtn.addEventListener("click", ()=>{
            sidebar.classList.toggle("open");
            menuBtnChange();//calling the function(optional)
            });

            searchBtn.addEventListener("click", ()=>{ // Sidebar open when you click on the search iocn
            sidebar.classList.toggle("open");
            menuBtnChange(); //calling the function(optional)
            });

            // following are the code to change sidebar button(optional)
            function menuBtnChange() {
            if(sidebar.classList.contains("open")){
            closeBtn.classList.replace("bx-menu", "bx-menu-alt-right");//replacing the iocns class
            }else {
            closeBtn.classList.replace("bx-menu-alt-right","bx-menu");//replacing the iocns class
            }
            }
        </script>
        </body>
    </main>
</template>

<style scoped>
    /* Google Font Link */
    @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@200;300;400;500;600;700&display=swap');
    *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: "Poppins" , sans-serif;
    }
    .sidebar{
    position: fixed;
    left: 0;
    top: 0;
    height: 100%;
    width: 78px;
    background: #000000;
    padding: 6px 14px;
    z-index: 99;
    transition: all 0.5s ease;
    }
    .sidebar.open{
    width: 250px;
    }
    .sidebar .logo-details{
    height: 60px;
    display: flex;
    align-items: center;
    position: relative;
    }
    .sidebar .logo-details .icon{
    opacity: 0;
    transition: all 0.5s ease;
    }
    .sidebar .logo-details .logo_name{
    color: #fff;
    font-size: 20px;
    font-weight: 600;
    opacity: 0;
    transition: all 0.5s ease;
    }
    .sidebar.open .logo-details .icon,
    .sidebar.open .logo-details .logo_name{
    opacity: 1;
    }
    .sidebar .logo-details #btn{
    position: absolute;
    top: 50%;
    right: 0;
    transform: translateY(-50%);
    font-size: 22px;
    transition: all 0.4s ease;
    font-size: 23px;
    text-align: center;
    cursor: pointer;
    transition: all 0.5s ease;
    }
    .sidebar.open .logo-details #btn{
    text-align: right;
    }
    .sidebar i{
    color: #fff;
    height: 60px;
    min-width: 50px;
    font-size: 28px;
    text-align: center;
    line-height: 60px;
    }
    .sidebar .nav-list{
    margin-top: 20px;
    height: 100%;
    }
    .sidebar li{
    position: relative;
    margin: 8px 0;
    list-style: none;
    }
    .sidebar li .tooltip{
    position: absolute;
    top: -20px;
    left: calc(100% + 15px);
    z-index: 3;
    background: #fff;
    box-shadow: 0 5px 10px rgba(0, 0, 0, 0.3);
    padding: 6px 12px;
    border-radius: 4px;
    font-size: 15px;
    font-weight: 400;
    opacity: 0;
    white-space: nowrap;
    pointer-events: none;
    transition: 0s;
    }
    .sidebar li:hover .tooltip{
    opacity: 1;
    pointer-events: auto;
    transition: all 0.4s ease;
    top: 50%;
    transform: translateY(-50%);
    }
    .sidebar.open li .tooltip{
    display: none;
    }
    .sidebar input{
    font-size: 15px;
    color: rgb(255, 255, 255);
    font-weight: 400;
    outline: none;
    height: 50px;
    width: 100%;
    width: 50px;
    border: none;
    border-radius: 12px;
    transition: all 0.5s ease;
    background: #7e96ff;
    }
    .sidebar.open input{
    padding: 0 20px 0 50px;
    width: 100%;
    }
    .sidebar li a{
    display: flex;
    height: 100%;
    width: 100%;
    border-radius: 12px;
    align-items: center;
    text-decoration: none;
    transition: all 0.4s ease;
    background: #241abb;
    }
    .sidebar li a:hover{
    background: #FFF;
    }
    .sidebar li a .links_name{
    color: #fff;
    font-size: 15px;
    font-weight: 400;
    white-space: nowrap;
    opacity: 0;
    pointer-events: none;
    transition: 0.4s;
    }
    .sidebar.open li a .links_name{
    opacity: 1;
    pointer-events: auto;
    }
    .sidebar li a:hover .links_name,
    .sidebar li a:hover i{
    transition: all 0.5s ease;
    color: #11101D;
    }
    .sidebar li i{
    height: 50px;
    line-height: 50px;
    font-size: 18px;
    border-radius: 12px;
    }
    .sidebar li.profile{
    position: fixed;
    height: 60px;
    width: 78px;
    left: 0;
    bottom: -8px;
    padding: 10px 14px;
    background: #1d1b31;
    transition: all 0.5s ease;
    overflow: hidden;
    }
    .sidebar.open li.profile{
    width: 250px;
    }
    .sidebar li .profile-details{
    display: flex;
    align-items: center;
    flex-wrap: nowrap;
    }
    .sidebar li img{
    height: 45px;
    width: 45px;
    object-fit: cover;
    border-radius: 6px;
    margin-right: 10px;
    }
    .sidebar li.profile .name,
    .sidebar li.profile .job{
    font-size: 15px;
    font-weight: 400;
    color: #fff;
    white-space: nowrap;
    }
    .sidebar li.profile .job{
    font-size: 12px;
    }
    .sidebar .profile #log_out{
    position: absolute;
    top: 50%;
    right: 0;
    transform: translateY(-50%);
    background: #1d1b31;
    width: 100%;
    height: 60px;
    line-height: 60px;
    border-radius: 0px;
    transition: all 0.5s ease;
    }
    .sidebar.open .profile #log_out{
    width: 60px;
    background: none;
    }
    .home-section{
    position: relative;
    background: #241abb;
    top: 0;
    left: 78px;
    width: calc(100% - 78px);
    transition: all 0.5s ease;
    z-index: 2;
    }
    .sidebar.open ~ .home-section{
    left: 250px;
    width: calc(100% - 250px);
    }
    .home-section .text{
    display: inline-block;
    color: #ffffff;
    font-size: 25px;
    font-weight: 500;
    margin: 18px
    }
    @media (max-width: 420px) {
    .sidebar li .tooltip{
        display: none;
    }
    }

</style>
