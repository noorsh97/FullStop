<template>
  <div class="footer">
    <div class="row">
      <div class="col-md-8 offset-md-2">
        <div class="row">
          <div class="col-6">
            <div class="fullStop">
              <span class="footerFull">FULL</span>
              <span class="footerCircle mt-3"> </span>
              <span class="footerStop">STOP</span>
            </div>
            <div>
              <p class="footerText">
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do
                eiusmod tempor incididunt ut labore et dolore magna aliqua.
              </p>
            </div>
            <div class="footerIconsContainer">
              <span class="icons"><i class="fab fa-linkedin-in"></i></span>
              <span class="icons"><i class="fab fa-pinterest-p"></i></span>
              <span class="twitterIcon icons"
                ><i class="fab fa-twitter"></i
              ></span>
              <span class="icons"> <i class="fab fa-facebook-f"></i></span>
            </div>
          </div>
          <div class="col-6">
            <div class="row">
              <div class="col-6">
                <li class="footerTitle">CATEGORIES</li>
                <ul
                  v-for="item in categories"
                  :key="item.id"
                  class="listWithoutBullets"
                >
                  <li>{{ item.name }}</li>
                </ul>
              </div>
              <div class="col-6">
                <ul class="listWithoutBullets">
                  <li class="footerTitle">COMPANY</li>
                  <li>Find Us</li>
                  <li>Help</li>
                  <li>FAQ</li>
                </ul>
              </div>
            </div>
          </div>
          <div class="row">
            <div class="col-12">
              <div class="copyright">
                Copyright @ 2017Vivek Popat. All rights reserved.
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Footer",
  props: ["categories"],
};
</script>

<style scoped>
.footer {
  position: fixed;
  left: 0;
  bottom: 0;
  color: #748a9d;
  width: 100%;
  box-shadow: 0 4px 10px 0 rgba(0, 0, 0, 0.4);
  transition: 0.3s;
  background-color: #ffffff;
  padding: 30px;
}

.firstColumn {
  margin-right: 185px;
  margin-bottom: 50px;
}

.listWithoutBullets {
  list-style-type: none;
  padding: 0px;
}
.listWithoutBullets > li {
  font-size: 16pt;
  text-align: left;
  margin-bottom: 12px;
}
.footerTitle {
  font-size: 16pt;
  font-weight: bold;
  text-align: left;
}

.footerFull {
  color: #7bed8d;
  font-size: 40pt;
  font-weight: bold;
}
.footerStop {
  color: #a6bcd0;
  font-size: 40pt;
  font-weight: bold;
}
.footerCircle {
  width: 49px;
  height: 49px;
  border: 1px solid #7bed8d;
  background-color: #7bed8d;
  border-radius: 49px;
  margin-inline: 10px;
  font-weight: bold;
}

.fullStop {
  text-align: left;
  margin-bottom: 20px;
  display: flex;
  flex-direction: row;
}
.footerText {
  width: 397px;
  text-align: left;
}
.copyright {
  font-size: 14pt;
}
.icons {
  color: #a6bcd0;
  font-size: 18pt;
  background-color: #f0f4f8;
  border: 2px solid #f0f4f8;
  border-radius: 40px;
  font-weight: bold;
  border-radius: 60px;
  margin-right: 10px;
  width: 40px;
  height: 40px;
  box-sizing: border-box;
}
.twitterIcon {
  color: #ffffff;
  background-color: #7bed8d;
  border: 2px solid #7bed8d;
  font-weight: bold;
}
.footerIconsContainer {
  display: flex;
  flex-direction: row;

  justify-content: flex-start;
}
</style>
