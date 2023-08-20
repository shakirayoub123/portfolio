<template>
  <div id="about">
    <div class="container">
      <div class="row">
        <div class="about-col-1">
          <img src="../assets/IMG_20230312_001125_915.jpg" alt="">
        </div>
        <div class="about-col-2">
          <h1 class="subtitle">About Me</h1>
          <p>I am currently working as a Front-end Developer at Ladybird Web Solution in Jammu. With strong
            problem-solving skills and extensive experience in creating and designing websites,I am highly motivated and
            skilled, with a Bachelor's degree in Computer Science and a passion for innovation</p>
          <div class="tab-titles">
            <p class="tab-links active-link" @click="(event) => openTab('skills', event)">Skills</p>
            <p class="tab-links" @click="(event) => openTab('education', event)">Education</p>
            <p class="tab-links" @click="(event) => openTab('experience', event)">Experience</p>
            <p class="tab-links" @click="(event) => openTab('internship', event)">Internship</p>
          </div>
          <div class="tab-contents active-tab" id="skills">
            <ul>
              <div class="tab-content" :class="{ active: activeTab === 'skills' }">
                <h2>Languages</h2>
                <div class="skills-buttons">
                  <button class="skills-button" v-for="(language, index) in programmingLanguages" :key="index"
                    :style="{ backgroundColor: getRandomColor() }">
                    {{ language }}
                  </button>
                </div>
              </div>
              <div class="tools-list">
                <h2>Tools</h2>
                <div class="skills-buttons">
                  <button class="skills-button tool-button" v-for="(tool, index) in toolsList" :key="index"
                    :style="{ backgroundColor: getRandomColor() }">
                    {{ tool }}
                  </button>
                </div>
              </div>


            </ul>
          </div>
          <div class="tab-contents" id="education">
            <ul>
              <li><span>Nov-2022 - Jan-2023</span><br /><br>MERN Stack Course from Masai School</li>
              <li><span>2016 - 2020</span><br /><br>Strengthened my expertise with B.Tech. in Computer Science from the
                University of Jammu.</li>
              <li><span>2015</span><br /><br>Built my knowledge base through Science Intermediate from the State Board.
              </li>
              <li><span>2013</span><br /><br>Matriculation from State Board</li>
            </ul>

          </div>
          <div class="tab-contents" id="experience">
            <ul>
              <li>
                <strong class="skills-button">Ladybird Web Solution</strong><br /><br />
                As a dedicated Front-end Developer at Ladybird Web Solution Pvt Ltd in Jammu, I play a pivotal role in
                crafting captivating user experiences. My responsibilities encompass translating design concepts into
                interactive and responsive web applications. Through my work, I contribute to creating impactful digital
                solutions that seamlessly merge aesthetics with functionality.
              </li>
              <h2>Skills Learned in LWS</h2>
              <div class="skills-buttons">
                <button class="skills-button" v-for="(language, index) in programmingLanguages" :key="index"
                  :style="{ backgroundColor: getRandomColor() }">
                  {{ language }}
                </button>
              </div>
            </ul>

          </div>
          <div class="tab-contents" id="internship">
            <ul>
              <strong class='skills-button'>Yarikul Infotech Srinagar</strong>
              <li><br /><br>
                I have learned HTML, CSS, JavaScript, and Bootstrap during my internship at Yarikul Infotech Srinagar.
                I also started working on my college project, where I took the opportunity to apply the skills I gained.
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
let tablinks = document.getElementsByClassName("tab-links")
let tabcontents = document.getElementsByClassName("tab-contents")
export default {
  name: 'About',
  data() {
    return {
      // ... other data properties
      programmingLanguages: [
        'HTML', 'CSS', 'JavaScript', 'ReactJs', 'VueJs', 'Bootstrap', 'Rest Api', 'Redux', 'Vuex', 'TDS'
      ],
      toolsList: [
        'Postman', 'IDE editors', 'Git', 'Netlify', 'Github', 'MySql', 'Xampp'
      ],
      showTools: false,
    };
  },

  methods: {
    getRandomColor() {
      const letters = '0123456789ABCDEF';
      let color = '#';
      for (let i = 0; i < 6; i++) {
        color += letters[Math.floor(Math.random() * 16)];
      }
      return color;
    },
    openTab(tabName, event) {
      for (let i = 0; i < tablinks.length; i++) {
        tablinks[i].classList.remove("active-link")
      }
      for (let i = 0; i < tabcontents.length; i++) {
        tabcontents[i].classList.remove("active-tab")
      }
      event.currentTarget.classList.add("active-link")
      document.getElementById(tabName).classList.add("active-tab")
    }
  },
}
</script>

<style scoped>
.tool-button {
  background-color: #ff004f;
}

.tool-button:hover {
  background-color: #d80045;
}

.skills-buttons {

  display: flex;
  flex-wrap: wrap;
  margin-top: 10px;
}

.skills-button {
  background-color: #ff004f;
  color: white;
  border: none;
  padding: 8px 15px;
  margin-right: 10px;
  margin-bottom: 10px;
  border-radius: 5px;
  font-size: 14px;
  cursor: pointer;
  transition: background-color 0.3s, transform 0.2s;
}

.skills-button:hover {
  background-color: #d80045;
  transform: scale(1.05);
}

#about {
  padding: 80px 0;
  color: #ababab;
}

.about-col-1 {
  flex-basis: 35%;
}

.about-col-1 img {
  width: 100%;
  border-radius: 15px;
}

.about-col-2 {
  flex-basis: 60%;
}

.tab-titles {
  display: flex;
  margin: 20px 0 40px;
}

.tab-links {
  margin-right: 50px;
  font-size: 18px;
  font-weight: 500;
  cursor: pointer;
  position: relative;
}

.tab-links::after {
  content: '';
  width: 0;
  height: 3px;
  background: #ff004f;
  position: absolute;
  left: 0;
  bottom: -8px;
  transition: 0.5s;
}

.tab-links.active-link:after {
  width: 50%;
}

.tab-contents ul li {
  margin: 10px 0;
}

.tab-contents ul li span {
  color: #b54769;
  font-size: 14px;
}

.tab-contents {
  display: none;
}

.tab-contents.active-tab {
  display: block;
}

@media only screen and (max-width: 600px) {
  #about {
    padding: 50px 0 25px;
  }

  .subtitle {
    font-size: 40px;
  }



  .row {
    display: flex;
    flex-direction: column;
  }

  .about-col-1 {
    text-align: center;
    margin-bottom: 15px;
  }

  .about-col-1 img {
    width: 100%;
  }

  .about-col-2 {
    font-size: 15px;
  }
}</style>