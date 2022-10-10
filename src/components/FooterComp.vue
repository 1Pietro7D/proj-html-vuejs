<template>
  <footer>
    <div class="getInTouch">
      <div class="max-container">
        <div class="about-blog">
          <h4>About the blog</h4>
          <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Laudantium,
            rem commodi ratione optio explicabo molestiae? Cupiditate,
            accusantium. Autem labore deserunt repellat quis adipisci atque
            alias similique ea sunt accusamus. Doloribus.
          </p>
          <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Sint
            repellat aut praesentium voluptatem ipsa asperiores vero minus
            quidem iste hic. Rerum atque aperiam asperiores autem dolor
            adipisci. Debitis, mollitia fugiat!
          </p>
          <h4>
            view more <font-awesome-icon icon="fa-solid fa-angle-right" />
          </h4>
        </div>

        <div>
          <h4>recent post</h4>
          <div class="d_flex">
            <img src="@/assets/img/our-office-4-square.jpg" alt="" />
            <div>
              <p>
                Lorem ipsum dolor, sit amet consectetur adipisicing elit. Quae
                corporis provident
              </p>
              <p>12:53 AM Dec 19th</p>
            </div>
          </div>
          <div class="d_flex">
            <img src="@/assets/img/our-office-5-square.jpg" alt="" />
            <div>
              <p>
                Lorem ipsum dolor, sit amet consectetur adipisicing elit. Quae
                corporis provident
              </p>
              <p>12:53 AM Dec 19th</p>
            </div>
          </div>
        </div>
        <div>
          <h4>recent comments</h4>
          <p>
            <font-awesome-icon icon="fa-solid fa-angle-right" />
            <span> John Doe</span>commented on
            <span>Lorem ipsum dolor lalala</span>
          </p>
          <p class="mb_1">12:55 AM Dec 19th</p>
          <p>
            <font-awesome-icon icon="fa-solid fa-angle-right" />
            <span> John Doe</span>commented on
            <span>Lorem ipsum dolor lalala</span>
          </p>
          <p class="mb_1">12:55 AM Dec 19th</p>
        </div>
        <div>
          <h4>categories</h4>
          <ul>
            <li>ops hehe</li>
            <li>ops hehe</li>
            <li>ops hehe</li>
            <li>ops hehe</li>
            <li>ops hehe</li>
            <li>ops hehe</li>
            <li>ops hehe</li>
            <li>ops hehe</li>
            <li>ops hehe</li>
            <li>ops hehe</li>
            <li>ops hehe</li>
            <li>ops hehe</li>
          </ul>
        </div>
      </div>
    </div>
    <div class="logo-footer">
      <div class="max-container">
        <div class="logo-copyright">
          <img src="@/assets/img/logo-footer.png" alt="" />
          <span>© Copyright 2020. All right Reserved</span>
        </div>
        <div class="contact">
          <div>
            <font-awesome-icon icon="fa-solid fa-angle-right" /><span
              >FAQ's</span
            >
          </div>
          <div>
            <font-awesome-icon icon="fa-solid fa-angle-right" /><span
              >Sitemap</span
            >
          </div>
          <div>
            <font-awesome-icon icon="fa-solid fa-angle-right" /><span
              >Contact us</span
            >
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: "FooterComp",
};
</script>

<style lang="scss" scoped>
@import "@/assets/style/variables.scss";
footer {
  color: rgb(108, 108, 108);
  .getInTouch {
    background-color: $footer_theme;
    padding: 5rem 0;
    .max-container {
      display: flex;
      .about-blog {
        width: 40%;
      }
    }
  }
  .logo-footer {
    background-color: $logo_footer_theme;
    padding: 2rem 0;

    .max-container {
      display: flex;
      justify-content: space-between;
      .logo-copyright {
        display: flex;
        align-items: center;
        gap: 3rem;
        img {
          height: 40px;
          margin-left: 2rem;
          filter: invert(0.3);
        }
      }
      .contact {
        margin-right: 2rem;
        display: flex;
        gap: 1.5rem;
        align-items: center;
      }
    }
  }
}
</style>
