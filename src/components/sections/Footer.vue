<template>
  <footer class="footer-wrapper">
    <div class="container">
      <div class="footer-wrapp">
        <div class="footer-left">
          <div class="decor">
            <img class="decor-img" src="/src/assets/img/decor.svg" alt="img" />
            <div class="line"></div>
            <div class="decor-text">Smarto</div>
          </div>
          <div class="contacts">
            <h2>Контакти</h2>
            <div class="contact-box">
              <div class="contact-item">
                <h3>Головний офіс:</h3>
                <a class="mail-link" href="mailto:SmartorangeTest@gmail.com">SmartorangeTest@gmail.com</a>
                <a href="https://maps.app.goo.gl/UTokfewuZkqrWRQT9" target="_blank" rel="noopener noreferrer" class="map">
                  Відкрити на Google maps
                </a>
              </div>
              <div class="contact-item">
                <h3>Наші соцмережі:</h3>
                <ul>
                  <li><a class="soc-link" href="https://www.instagram.com/" target="_blank" rel="noopener noreferrer"><img src="/src/assets/img/social-1.svg" alt="icon" /></a></li>
                  <li><a class="soc-link" href="https://www.youtube.com/" target="_blank" rel="noopener noreferrer"><img src="/src/assets/img/social-2.svg" alt="icon" /></a></li>
                  <li><a class="soc-link" href="https://www.facebook.com/" target="_blank" rel="noopener noreferrer"><img src="/src/assets/img/social-3.svg" alt="icon" /></a></li>
                  <li><a class="soc-link" href="https://ukr.radio/news.html?newsID=102587" target="_blank" rel="noopener noreferrer"><img src="/src/assets/img/social-4.svg" alt="icon" /></a></li>
                </ul>
              </div>
            </div>
            <div class="contact-box">
              <div class="contact-item">
                <h3>Телефони відділів:</h3>
                <div class="phone">
                  <a class="phone-link" href="tel:+380444444444">(044) 444-44-44</a><span>( Юридичний відділ )</span>
                </div>
                <div class="phone">
                  <a class="phone-link" href="tel:+380555555555">(055) 555-55-55</a><span>( Бухгалтерія )</span>
                </div>
              </div>
              <div class="contact-item">
                <h3>Email:</h3>
                <a class="mail-link" href="mailto:office@smarto.ua">office@smarto.ua</a>
              </div>
            </div>
          </div>
        </div>
        <div class="footer-right">
          <div class="footer-right-wrapp">
            <div class="footer-right-text">
              <div class="right-text-1">Якість</div>
              <div class="right-text-2">понад усе</div>
            </div>
            <div class="foot-img-wrapp foot-img-1">
              <img src="/src/assets/img/footer-img-2.png" alt="img" />
            </div>
            <div class="foot-img-wrapp foot-img-2">
              <img src="/src/assets/img/footer-img-1.png" alt="img" />
            </div>
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>

<script setup>

</script>

<style lang="scss">
.footer-wrapper {
  margin-bottom: clamp(80px, 10vw, 200px);
  .footer-wrapp {
    display: flex;
    flex-wrap: wrap;
    gap: clamp(30px, 5vw, 90px);
    .footer-left {
      flex: 1 1 600px;
      .decor {
        display: flex;
        gap: clamp(10px, 1.5vw, 23px);
        margin-bottom: clamp(15px, 2vw, 25px);
        .line {
          position: relative;
          width: 100%;
          max-width: 744px;
          &::before {
            content: "";
            position: absolute;
            top: 50%;
            left: 0;
            width: 100%;
            height: 1px;
            background-color: $black;
          }
        }
        .decor-text {
          font-weight: 500;
          font-size: clamp(10px, 0.8vw, 14px);
          line-height: 140%;
          text-transform: uppercase;
        }
      }
      .contacts {
        display: grid;
        grid-template-columns: 1fr 1fr;
        column-gap: clamp(40px, 5vw, 80px);
        row-gap: clamp(24px, 3vw, 40px);
        align-items: start;

        h2 {
          grid-column: 1 / -1;
          font-weight: 400;
          font-size: clamp(40px, 5vw, 96px);
          line-height: 90%;
          margin-bottom: clamp(30px, 4vw, 83px);
        }
        .contact-box {
            display: contents;
          .contact-item {
            display: flex;
            flex-direction: column;
            font-weight: 500;
            font-size: clamp(16px, 1vw, 20px);
            line-height: 120%;

            h3 {
              font-weight: 600;
              font-size: clamp(18px, 1.25vw, 24px);
              margin-bottom: clamp(10px, 1vw, 23px);
            }
            .map {
              font-weight: 500;
              font-size: clamp(10px, 0.8vw, 14px);
              line-height: 140%;
              text-transform: uppercase;
              background-color: $black;
              padding: clamp(8px, 1vw, 13px) clamp(12px, 1.5vw, 20px);
              color: $white;
              border-radius: 100px;
              margin-top: clamp(20px, 3vw, 41px);
              width: fit-content;
              transition: transform 0.3s ease;
              &:hover {
                transform: scale(1.03);
              }
            }
            ul {
              display: flex;
              gap: 6px;
              li {
                .soc-link {
                  img {
                    transition: transform 0.3s ease;

                    &:hover {
                      transform: scale(1.08);
                    }
                  }
                }
              }
            }
            .phone {
              font-size: clamp(14px, 1vw, 20px);
              margin-bottom: 15px;
              position: relative;
              padding-left: clamp(20px, 1.5vw, 26px);
              &::before {
                content: "";
                position: absolute;
                top: 10px;
                left: 0;
                transform: translateY(-50%);
                width: clamp(14px, 2vw, 16px);
                height: clamp(14px, 2vw, 16px);
                background-image: url(/src/assets/img/phone.svg);
                background-size: contain;
                background-repeat: no-repeat;
                background-position: center;
              }
              .phone-link {
                display: inline-block;
                white-space: nowrap;
                transition: transform 0.2s ease;
                &:hover {
                  transform: translateY(-1px);
                }
              }
              span {
                font-size: 14px;
                text-transform: uppercase;
                color: $grey;
                margin-left: 12px;
                white-space: nowrap;
              }
            }
            .mail-link {
              transition: transform 0.2s ease;
              &:hover {
                transform: translateY(-1px);
              }
            }
          }
        }
      }
    }
    .footer-right {
      flex: 1 1 600px;
      .footer-right-wrapp{
        width: 100%;
        position: relative;
          .footer-right-text {
          position: relative;
          font-weight: 400;
          font-size: clamp(28px, 5vw, 96px);
          line-height: 90%;
          z-index: 3;
          color: white;
          mix-blend-mode: difference;
          .right-text-1 {
            position: absolute;
            top: clamp(20px, 3vw, 50px);
            right: clamp(40px, 30vw, 583px);
          }
          .right-text-2 {
            position: absolute;
            top: clamp(188px, 28vw, 544px);
            right: clamp(60px, 8vw, 150px); 
          }
        }
        .foot-img-wrapp {
          position: absolute;
          width: 100%;
          max-width: clamp(230px, 35vw, 680px);
          height: auto;
          img {
            width: 100%;
            height: auto;
          }
        }
        .foot-img-1 {
          right: clamp(15px, 8vw, 0px);
          top: 0;
        }
        .foot-img-2 {
          right: clamp(55px, 8vw, 150px);
          top: 0;
        }
      }
    }
  }

  @media (max-width: 1370px) {
    .footer-wrapp {
      justify-content: center;
    }
    .footer-wrapp .footer-left{
      margin-bottom: 30px;
    }
    .footer-wrapp .footer-right {
      flex: 0 0 clamp(300px, 35vw, 680px);
      margin-bottom: 400px;
    }
  }

  @media (max-width: 825px) {
    .footer-wrapp .footer-left .contacts {
      grid-template-columns: 1fr;
      justify-items: start;
    }
    .footer-wrapp .footer-right .footer-right-wrapp .footer-right-text .right-text-1 {
      position: absolute;
      top: clamp(20px, 3vw, 50px);
      left: 19px;
    }
  }
  @media (max-width: 420px){
    .footer-wrapp .footer-left .contacts .contact-box .contact-item .phone span {
      font-size: 12px;
    }
  }
}
</style>