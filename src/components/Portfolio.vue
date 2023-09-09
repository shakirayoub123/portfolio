<template>
  <div id="services">
    <div class="container">
      <h1 class="subtitle">My Projects</h1>

      <div class="services-list">
        <div v-for="item in items" :key="item.id">
          <h3 class="project">{{ item.name }}</h3>
          <p>{{ item.description }}</p>
          <p>{{ item.tools }}</p>
          <p>
            <a :href="item.tools" target="_blank" rel="noopener noreferrer">
              <i class="fa-brands fa-github icons"></i>
            </a>
            &nbsp;&nbsp; <!-- Use a separator, e.g., a pipe symbol (|) with spaces -->
            <a :href="item.live" target="_blank" rel="noopener noreferrer">
              <i class="fa-brands fa-deploydog" icons></i>
            </a>
          </p>
        </div>


      </div>
    </div>
  </div>
</template>
  
<script>
import { data } from '../data'

export default {
  data() {
    return {
      items: data.items,
    };
  },
  created() {
    console.log('Fake response data:', this.items);
  },
};
</script>
  
<style scoped>
.project {
  font-weight: bold;
 margin-bottom: 10px;
}

/* Add your CSS styles here */
#services {
  padding: 30px 0 25px;
}

.services-list {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 40px;
  margin-top: 50px;
}

.services-list div {
  background: #262626;
  padding: 40px;
  font-size: 13px;
  font-weight: 300;
  border-radius: 10px;
  transition: all .5s;
}
.services-list div:hover {
  background: #4f4f4f;
  transform: translateY(-10px);
  box-shadow: -5px -5px 30px 5px red, 5px 5px 30px 5px blue;/* Adjust the box shadow on hover */
}
.services-list div i {
  font-size: 20px;
  margin-bottom: 10px;
}

.services-list h2 {
  font-size: 30px;
  font-weight: 500;
  margin-bottom: 15px;
}

.services-list p {
  margin-bottom: 15px;
}

.services-list div:hover {
  background: #4f4f4f;
  ;
  transform: translateY(-10px);
}

@media only screen and (max-width: 600px) {
  #services {
    padding: 30px 0 20px;
  }

  .services-list {
    gap: 25px;
  }

  .services-list div i {
    font-size: 28px;
    margin-bottom: 20px;
  }

  .services-list div h2 {
    font-size: 25px;
  }

  .services-list div,
  .services-list div a,
  .services-list div a i {
    font-size: 12px;
    letter-spacing: .01rem;
  }

  h1 {
    font-size: 50px;
  }

  .services-list {
    margin-top: 25px;
  }
}
</style>
  