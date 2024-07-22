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
                        <h2 class="font"> {{ jumlahpengunjung}} Pengunjung</h2>                    </div>
                </div>
                </nuxt-link>
            </div>
        
            <div class="col-lg-6">
                <nuxt-link to="/buku">
                <div class="card bg-success rounded-5">
                    <div class="card-body">
                        <h6 class="font"> {{jumlahbuku}} Buku </h6>
                    </div>
                </div>
                </nuxt-link>
            </div>
        </div>
        <Chart/>
    </div>
</template>

<script setup>
const supabase = useSupabaseClient();
const jumlahpengunjung = ref (0);
const jumlahbuku = ref (0);


async function ambiljumlahpengunjung() {
    const { data,error, count} = await supabase
    .from("pengunjung")
    .select("*", {count: 'exact'});
    if (count) jumlahpengunjung.value = count;
}
async function ambiljumlahbuku() {
    const { data,error, count} = await supabase
    .from("buku")
    .select("*", {count: 'exact'});
    if (count) jumlahbuku.value = count;
}


onMounted(() => {
    ambiljumlahpengunjung();
    ambiljumlahbuku();
})
</script>





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
    color: rgb(255, 255, 255);
    font-size: 30px;
    margin: 15px;
    
}

h2 {
    color: rgb(255, 255, 255);
    font-size: 30px;
    text-align: center;
    margin: 70px;
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
    color: rgb(255, 255, 255);
    justify-content: center;
    font-size: 30px;
}

h6 {
    color: rgb(255, 255, 255);
    font-size: 30px;
    text-align: center;
    margin: 70px;
}

</style>