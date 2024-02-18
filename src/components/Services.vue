<template>
    <div id="services">
        <div class="container">
            <h1 class="subtitle">My Services</h1>
            <div class="services-list">
                <div>
                    <i class="fas fa-code"></i>
                    <h2>Front-End Development</h2>
                    <p>Passionate about creating beautiful and intuitive web interfaces.</p>
                </div>
                  <div>
                        <i class="fas fa-crop-alt"></i>
                        <h2>Backend Development</h2>
                        <p>Continuously expanding my knowledge in backend development, as started working on NodeJs and Laravel</p>
                    </div>
                </div>
            </div>
        </div>
</template>

<script>
export default {
    name: 'Services'
}
</script>

<style scoped>
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

.services-list div i {
    font-size: 50px;
    margin-bottom: 30px;
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
    transform: translateY(-10px);
    box-shadow: -5px -5px 30px 5px red, 5px 5px 30px 5px blue;
    /* Adjust the box shadow on hover */
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