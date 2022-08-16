<template>
	<nav class="navbar">
		<div class="navbar-toggle hamburger-lines" id="js-navbar-toggle" @click="showMobileMenu = !showMobileMenu">
              <span class="line line1" :style="[showMobileMenu ? {transform: 'rotate(45deg)'} : {}]"></span>
              <span class="line line2" :style="[showMobileMenu ? {transform: 'scaleY(0)'} : {}]"></span>
              <span class="line line3" :style="[showMobileMenu ? {transform: 'rotate(-45deg)'} : {}]"></span>
            </div>  
		<a href="#" class="logo">logo</a>
		<ul class="main-nav" id="js-menu" :style="[showMobileMenu ? {display: 'block'} : {display: 'none'}]">
			<li>
				<a href="#" class="nav-links">Home</a>
			</li>
			<li>
				<a href="#" class="nav-links">Products</a>
			</li>
			<li>
				<a href="#" class="nav-links">About Us</a>
			</li>
			<li>
				<a href="#" class="nav-links">Contact Us</a>
			</li>
			<li>
				<a href="#" class="nav-links">Blog</a>
			</li>
		</ul>
  	</nav>
</template>

<script>

export default {
	name: 'Header',
	components: {
		
	},
	props: {
		null: null
	}, 
	data() {
        return {
			showMobileMenu: false,
        };
    },
	methods:{
		
	},
}

</script>

<style scoped>
.navbar {
  font-size: 18px;
  border: 1px solid rgba(0, 0, 0, 0.2);
  padding-bottom: 10px;
  border-bottom: 1px solid rgba(160,159,159,.336);
  background-color: #f8f9fa;
  color: rgba(0,0,0,.5);
  font-family: Montserrat, sans-serif;
}

.main-nav {
  list-style-type: none;
  display: none;
  padding: 0;
}

.nav-links,
.logo {
  text-decoration: none;
  color: rgba(0,0,0,.5);
}

.main-nav li {
  text-align: center;
  margin: 15px auto;
}

.logo {
  display: inline-block;
  font-size: 22px;
  margin-top: 10px;
  margin-left: 20px;
}

.navbar-toggle {
  position: absolute;
  top: 10px;
  right: 20px;
  cursor: pointer;
  color: rgba(255, 255, 255, 0.8);
  font-size: 24px;
}
.hamburger-lines {
  display: block;
  height: 26px;
  width: 32px;
  z-index: 2;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  transform: translateX(0);
}

.hamburger-lines .line {
  display: block;
  height: 4px;
  width: 100%;
  border-radius: 10px;
  background: #0e2431;
}

.hamburger-lines .line1 {
  transform-origin: 0% 0%;
  transition: transform 0.4s ease-in-out;
}

.hamburger-lines .line2 {
  transition: transform 0.2s ease-in-out;
}

.hamburger-lines .line3 {
  transform-origin: 0% 100%;
  transition: transform 0.4s ease-in-out;
}

@media screen and (min-width: 768px) {
  .navbar {
    display: flex;
    justify-content: space-between;
    padding-bottom: 0;
    height: 70px;
    align-items: center;
  }

  .main-nav {
    display: flex !important;
    margin-right: 30px;
    flex-direction: row;
    justify-content: flex-end;
  }

  .main-nav li {
    margin: 0;
  }

  .nav-links {
    margin-left: 40px;
  }

  .logo {
    margin-top: 0;
  }

  .navbar-toggle {
    display: none;
  }

  .logo:hover,
  .nav-links:hover {
    color: rgba(255, 255, 255, 1);
  }
}
</style>
