<template>
  <Layout :show-logo="false">
    <div class="cv__container">
      <div class="cv__content">
        <h1>Jose Gabriel Silva</h1>
        <h3>Software Engineer</h3>
        <div class="cv__intro">
          <div class="cv__intro_item">
            <icon-email></icon-email>
            <span>
              <a href="mailto:jose@lunite.net" target="_blank">jose@lunite.net</a>
            </span>
          </div>
          <div class="cv__intro_item">
            <icon-map></icon-map>
            <span>Formosa, Argentina</span>
          </div>
          <div class="cv__intro_item">
            <icon-link></icon-link>
            <span>
              <a href="https://josesilva.dev/" target="_blank">josesilva.dev</a>
            </span>
          </div>
        </div>

        <div class="cv__work">
          <div class="cv__section">
            <h2>Work Experience</h2>
            <div class="cv__section_separator"></div>
          </div>
          <div class="cv__work_item">
            <div class="cv__work_item_title">
              <span class="font-bold">Senior Frontend Developer @ <a href="https://agileengine.com/" target="_blank">Agile Engine</a></span>
              <span class="date">May 2021 - Present</span>
            </div>
            <div class="cv__work_item_content">
              <p>Project: Dialpad – Cloud-based voice intelligence software.</p>
              <p><a href="https://github.com/dialpad/dialtone/commits?author=josedialpad" target="_blank">Dialtone</a> - Design system for Dialpad and Dialpad Meetings.</p>
              <p><a href="https://github.com/dialpad/dialtone-vue/commits?author=josedialpad" target="_blank">Dialtone Vue</a> - Dialtone Vue is a library of Vue components for Dialtone</p>
              <ul>
                <li>Develop new components and maintain the component library.</li>
                <li>Support to product developers related to the usage of the Design System.</li>
                <li>Migration of the breaking changes in the products.</li>
              </ul>
            </div>
          </div>
          <div class="cv__work_item">
            <div class="cv__work_item_title">
              <span class="font-bold">Software Engineer @ <a href="https://graff3d.com/" target="_blank">Graff3D</a></span>
              <span class="date">Apr 2020 - Apr 2021</span>
            </div>
            <div class="cv__work_item_content">
              <p>Project: <a href="https://graff3d.com/web-3d/" target="_blank">Web3D</a> – Real estate project visualization in the most interactive and realistic way.</p>
              <ul>
                <li>I've worked on building Web3D, a platform to visualize and give the best experience to sell a real estate unit.</li>
              </ul>
            </div>
          </div>
          <div class="cv__work_item">
            <div class="cv__work_item_title">
              <span class="font-bold">Full-Stack Engineer @ <a href="https://www.dataproviders.io/" target="_blank">Data Providers</a></span>
              <span class="date">Feb 2019 - Jan 2020</span>
            </div>
            <div class="cv__work_item_content">
              <p><a href="https://console.dataproviders.io/#/login" target="_blank">Data Providers</a> – Platform that provides cloud data tools to manage, process, analyze, visualize and share information.</p>
              <ul>
                <li>I've worked in DataProviders building the tool from scratch, using modern web technologies and taking part in several architectural decisions.</li>
              </ul>
            </div>
          </div>
          <div class="cv__work_item">
            <div class="cv__work_item_title">
              <span class="font-bold">Web Developer @ <a href="https://42mate.com/" target="_blank">42mate</a></span>
              <span class="date">Aug 2018 - Jan 2020</span>
            </div>
            <div class="cv__work_item_content">
              <p>Project: <a href="https://www.apple.com/" target="_blank">Apple</a></p>
              <p><a href="https://42mate.com/success-stories/apple/" target="_blank">Testing dashboard and reporting tool</a></p>
              <ul>
                <li>I've worked for different projects using a variety of technologies like PHP with Laravel Framework, Javascript vanilla and also with the Framework Vue.js</li>
              </ul>
            </div>
          </div>
        </div>

        <div class="cv__education">
          <div class="cv__section">
            <h2>Education</h2>
            <div class="cv__section_separator"></div>
          </div>
          <div class="cv__education_item">
            <div class="cv__education_item_title">
              <span class="font-bold">Information Systems Engineering @ UTN FRRe</span>
              <span class="date">2014 - 2020</span>
            </div>
          </div>
          <div class="cv__education_item">
            <div class="cv__education_item_title">
              <span>IELTS Indicator Score: 6.5 (B2)</span>
              <span class="date">2021</span>
            </div>
          </div>
        </div>

        <div class="cv__skills">
          <div class="cv__section">
            <h2>Skills</h2>
            <div class="cv__section_separator"></div>
          </div>
          <div class="cv__skills_item">
            <table class="cv__skills_table">
              <tbody>
                <tr>
                  <td>Languages and Frameworks</td>
                  <td>JavaScript, Vue.js, Vuex, Vue Router, HTML, CSS, jQuery, Node.js, Jest, Cypress, Python, Django, PHP, Laravel, JSON, JSON Web Tokens, GraphQL, Bash, Websockets;</td>
                </tr>
                <tr>
                  <td>OS & Platforms</td>
                  <td>Google Cloud Platform, DigitalOcean, Linux (Ubuntu, Debian, Alpine), Docker;</td>
                </tr>
                <tr>
                  <td>DBMS</td>
                  <td>MySQL, MariaDB, PostgreSQL;</td>
                </tr>
                <tr>
                  <td>VCS, Build, CI/CD</td>
                  <td>Git, Gitlab CI/CD, GitHub, Travis CI, Apache;</td>
                </tr>
                <tr>
                  <td>Tools and Libraries</td>
                  <td>Electron, Nginx, Kong;</td>
                </tr>
                <tr>
                  <td>Methodologies</td>
                  <td>Agile (Scrum);</td>
                </tr>
              </tbody>
            </table>
          </div>
        </div>
      </div>
    </div>
  </Layout>
</template>

<script>
import IconEmail from '@/assets/icons/email';
import IconMap from '@/assets/icons/map';
import IconLink from '@/assets/icons/link';
export default {
  components: {
    IconEmail,
    IconLink,
    IconMap,
  },
  metaInfo: {
    titleTemplate: 'José Silva',
  }
}
</script>

<style lang="scss">
.font-bold {
  font-weight: bold;
}

.date {
  color: #858585;
}

.cv__container {
  background-color: #fff;
  width: 100%;
  max-width: 1000px;
  margin: 0 auto;

  a {
    text-decoration: none;
    color: #003291;
  }
}

.cv__content {
  padding: 25px 30px;
  color: #000;

  h1 {
    color: #000;
    margin-bottom: 5px;
  }

  h2 {
    color: #000;
    margin-top: 20px;
    margin-bottom: 5px;
  }

  h3 {
    color: #525252;
    margin-top: 0px;
  }

  .cv__section {
    display: flex;
    align-items: center;
    margin: 20px 0 5px;

    h2 {
      margin: 0;
    }
  }

  .cv__section_separator {
    flex-grow: 1;
    height: 2px;
    margin-left: 15px;
    min-width: 0;
    box-sizing: border-box;
    background-color: #0f2d44;
  }

  .cv__intro {
    margin-top: 20px;
    display: flex;
    flex-flow: row wrap;
    justify-content: space-between;
  }

  .cv__intro_item {
    display: flex;
    flex-direction: row;
    align-items: center;
    gap: 5pt;
  }

  .cv__work_item_title,
  .cv__education_item_title {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 5px;
  }

  .cv__work_item_content,
  .cv__education_item_content {
    p {
      margin-bottom: 5px;
    }

    ul {
      li {
        margin-bottom: 2px;
      }
    }
  }

  .cv__skills_table {
    border-spacing: 0;

    tr td {
      border: 1px solid #d9d9d9;
      padding: 5px 8px;
      vertical-align: middle;
    }

    tr td:first-child {
      font-weight: bold;
      background-color: #f5f5f5;
    }
  }
}
</style>
