<template>
  <div>
    <div class="home">
      <div class="hero">
        <p class="action">
          <a :href="$withBase('/guide/diboot-core/安装.html')" class="button white">快速上手</a>
          <i class="fa fa-2x fa-play-circle" aria-hidden="true"></i>

          <a href="https://devtools-v2.diboot.com/antd/" class="button white" target="_blank">Antd项目案例</a>
          <i class="fa fa-2x fa-play-circle" aria-hidden="true"></i>

          <a :href="$withBase('https://devtools-v2.diboot.com/element/')" class="button white" target="_blank">Element项目案例</a>
          <i class="fa fa-2x fa-play-circle" aria-hidden="true"></i>

          <a href="javascript:;" class="button has-icon" @click="showVideo">
            <img class="icon" src="../public/play-circle.png" alt="">
            了解 diboot 2.0
          </a>
        </p>
      </div>
      <div class="custom content">
        <div class="features">
          <div class="feature col-1">
            <h2>diboot-core 精简高效内核</h2>
            <p>
              <ul>
                  <li>单表CRUD无SQL</li>
                  <li>关联查询无SQL - 注解自动绑定</li>
                  <li>数据字典无SQL - 注解自动绑定</li>
                  <li>Entity/DTO自动转换查询对象</li>
                  <li>常用工具类的最佳实践封装</li>
              </ul>
            </p>
          </div>
          <div class="feature col-2">
            <h2>diboot-devtools 强大开发助理</h2>
            <p>
                <ul>
                    <li>支持多数据库（MySQL、MariaDB、ORACLE、SQLServer、PostgreSQL）</li>
                    <li>使用很简单（引入依赖jar，配置参数后，即可随SpringBoot启动运行）</li>
                    <li>功能很强大（数据结构变更与代码联动同步，一键生成/更新代码，自动记录变更SQL）</li>
                    <li>配置很灵活（可按需配置生成代码是否启用`Lombok`、`Swagger`、`Shiro`等）</li>
                    <li>代码很标准（devtools标准化了数据结构定义与代码实现，降低维护成本）</li>
                </ul>
            </p>
          </div>
        </div>
      </div>
      <div class="custom content">
        <div class="features">
          <img src="../public/structure.png" alt="" style="display: block; margin: 0 auto; width: 100%; height: auto;">
        </div>
      </div>
      <div class="footer">
        <div class="footer-content">
          <div class="footer-item"></div>
          <div class="footer-item">
            <h4>QQ群: 731690096</h4>
            <img src="../public/add_qqqun.png" alt="" width="120">
          </div>
          <div class="footer-item">
            <h4>微信群: wx20201024</h4>
            <img src="../public/add_wechat.png" alt="" width="120">
          </div>
          <div class="footer-item">
          </div>
        </div>
        <p class="copy-right">© 2015-2020 <a href="http://www.dibo.ltd">苏州帝博信息技术有限公司</a>
          <br>
          <a class="ba-a" href="http://www.beian.miit.gov.cn/" target="_blank">
            <u>
              苏ICP备15013001号
            </u>
          </a>
        </p>
      </div>
    </div>

    <div class="modal-cover" v-show="showModal" @click="closeModal">
      <div class="modal-content" @click="onModalContentClick($event)">
        <video src="https://diboot.oss-cn-shanghai.aliyuncs.com/file/%E5%BC%80%E5%A7%8B%E4%BD%BF%E7%94%A8diboot%E4%B8%8E%E5%85%B3%E8%81%94%E6%BC%94%E7%A4%BA_%E5%AD%97%E5%B9%95.mp4?nsukey=Z8MYZulBJM0GZXYNQgYGJGxRDvYMIWMsGj%2FkV%2BQpZD2aN7hsk7hreW1mXv71kxX7W5Sd61warYIPAAT4xDifYZEv3cQiiQiVW%2BqF%2FqomaxhPm1ht5jV5YkWLGiwcqQKeHmN5jn9%2FRWzaWTNweSZjWuif%2FZIciG6BX8UddZ0klnyyGfrtdB2eWCBAh%2F5n5rMPGdyUhYXAzzDsdPtyBxcY7w%3D%3D"
            class="homeVideo" id="homeVideo" controls>
        </video>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: "HomeLayout",
    data () {
      return {
        showModal: false
      }
    },
    methods: {
      showVideo () {
        this.showModal = true
        document.querySelector("#homeVideo").play()
      },
      closeModal () {
        this.showModal = false
        document.querySelector("#homeVideo").pause()
      },
      onModalContentClick(e){
        e.preventDefault()
        e.stopPropagation()
      }
    }
  }
</script>

<style scoped lang="stylus" rel="stylesheet">
.home {
  padding: 0 2rem 0;
  max-width: 1160px;
  margin: 0 auto;
  .hero {
    text-align: center;
    .action {
      margin: 1.6rem auto;
    }
    .action-button {
      display: inline-block;
      font-size: 1.2rem;
      color: #fff;
      background-color: #3eaf7c;
      padding: .8rem 1.6rem;
      border-radius: 4px;
      transition: background-color .1s ease;
      border-bottom: #3eaf7c;
    }
    .action-button:hover {
      background-color: #4abf8a;
    }
  }
  .content.custom {
    padding: 0;
    margin: 0;
  }
  .features {
    border-top: 1px solid #eaecef;
    padding: 1.2rem 0;
    margin-top: 2.5rem;
    display: flex;
    flex-wrap: wrap;
    align-items: flex-start;
    align-content: stretch;
    justify-content: space-between;
  }
  .feature {
    flex-grow: 1;
    flex-basis: 30%;
    max-width: 50%;
    h2 {
      font-size: 1.4rem;
      font-weight: 500;
      border-bottom: none;
      padding-bottom: 0;
      color: #3a5169;
    }
    p {
      color: #4e6e8e;
    }
  }
  .footer {
    padding: 1rem 2.5rem .5rem 2.5rem;
    border-top: 1px solid #eaecef;
    text-align: left;
    color: #4e6e8e;
    .footer-content {
      display: flex;
      flex-wrap: wrap;
      align-items: flex-start;
      align-content: stretch;
      justify-content: space-between;
      .footer-item {
        flex-grow: 1;
        flex-basis: 25%;
        max-width: 25%;
        text-align: center;
        h4 {
          font-size: 18px;
          font-weight: 400;
          border-bottom: none;
          padding-bottom: 0;
          color: #3a5169;
          margin: 10px 0;
        }
        ul {
          list-style: none;
          padding: 0;
        }
      }
    }
    p.copy-right {
      padding-top: 20px;
      text-align: center;
      border-top: 1px solid #eaecef;
    }
  }
}


a.button {
  padding: 0.75em 2em;
  border-radius: 2em;
  display: inline-block;
  color: #fff;
  background-color: #4fc08d;
  transition: all 0.15s ease;
  box-sizing: border-box;
  border: 1px solid #4fc08d;
  font-size: 1.05em;
  font-weight: 600;
  letter-spacing: 0.1em;
  min-width: 8em;
  text-align: center;
}
a.button.has-icon {
  position: relative;
  text-indent: 1.4em;
}
a.button.has-icon > .icon {
  position: absolute;
  left: 15px;
  top: 15px;
  margin: 0;
  width: 26px;
}
a.button.white {
  background-color: #fff;
  color: #42b983;
  margin-right: 30px;
}

.modal-cover{
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.2);
  z-index: 1000;
  position: fixed;
  top: 0;
  left: 0;
  text-align: center;
  font-size: 16px;
  box-shadow: 0 0 5px black;
}
.modal-content{
  position: fixed;
  width: 1180px;
  height: 666px;
  top: 50%;
  left: 50%;
  margin-top: -333px;
  margin-left: -590px;
  z-index: 1100;
  background-color: white;
  box-shadow: 0 0 15px black;
}
.homeVideo{
  height: 666px;
}
.donate-image{
  display: block;
  margin: 10px auto;
  width: 500px;
  height: auto;
}
.feature.col-1{
  max-width: 35%;
}
.feature.col-2{
  max-width: 60%;
}
.ba-line{
  margin: 0;
  line-height: 28px;
  text-align: center;
}
.copy-right .ba-a{
  font-size: 16px;
  color: #999;
}
@media screen and (max-width: 750px) {
  .button.has-icon{
    display: block;
    margin-top: 5px;
  }
  .home {
    padding: 0;
  }
  .home .feature{
    padding: 0;
  }
  .feature.col-1{
    max-width: 100%;
  }
  .feature.col-2{
    max-width: 100%;
  }
  .home .footer{
    padding: 1rem 0;
  }
  .home .footer .footer-content .footer-item{
    max-width: 100%;
    flex-basis: 100%;
  }
  .modal-content{
    width: 320px;
    height: 180px;
    margin-top: -90px;
    margin-left: -160px;
  }
  .homeVideo{
    height: 180px;
  }
  a.button.white{
    display: block;
    margin-bottom: 10px;
    margin-right: 0;
  }
}
</style>