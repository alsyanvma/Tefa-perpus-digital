<template>
    <div class="container-fluid">
        <div class="row my-5">
            <div class="col-lg-6">
                <nuxt-link to="/pengunjung/tambah">
                    <div class="card bg-pengunjung rounded-5">
                        <div class="card-body">
                            <h5>Pengunjung</h5>
                        </div>
                    </div>
                </nuxt-link>
            </div>

            <div class="col-lg-6">
                <nuxt-link to="/buku">
                    <div class="card bg-buku rounded-5">
                        <div clas="card-body">
                            <h1>Cari Buku</h1>
                        </div>
                    </div>
                </nuxt-link>
            </div>
        </div>
        <h1 class="statistik">STATISTIK</h1>
        <div class="row my-5">
            <div class="col-lg-6">
                <nuxt-link to ="/pengunjung">
                <div class="card bg-warning rounded-5">
                    <div class="card-body">
                        <div class="angka-statistik">32 <span class="label-statistik">Pengunjung</span></div>
                    </div>
                </div>
                </nuxt-link>
            </div>
        
            <div class="col-lg-6">
                <nuxt-link to="/buku">
                <div class="card bg-success rounded-5">
                    <div class="card-body">
                        <div class="angka-statistik">180 <span class="label-statistik">Buku</span></div>
                    </div>
                </div>
                </nuxt-link>
            </div>
        </div>
        <Chart/>
    </div>
</template>


<style scoped>
.card {
    height: 250px;
    box-shadow: 1px 1px 10px #424242;
}

.card.bg-pengunjung {
    background-image: url('../assets/img/bg-home-kunjungan.jpeg');
    background-repeat: no-repeat;
    background-position: center center;
    background-size: cover;
    
}

.card.bg-buku {
    background-image: url('../assets/img/bg-home-cari-buku.jpg');
    background-repeat: no-repeat;
    background-position: center center;
    background-size: cover;
    
}

.angka-statistik {
    color: black;
    text-align: center;
    font-size: 80px;
    margin: 15px;
}

.label-statistik {
    font-size: 50px;
}

h1 {
    color: black;
    font-size: 30px;
}

h3 {
    color: black;
    font-size: 70px;
    text-align: center;
    margin: 40px;
    opacity: 80%;
}

h4 {
    color: black;
    font-size: 70px;
    text-align: center;
    margin: 40px;
    opacity: 80%;
}

h5{
    color: black;
    justify-content: center;
    font-size: 30px;
}

</style>