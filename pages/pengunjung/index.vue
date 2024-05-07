<template>
    <div class="container-fluid">
        <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.11.3/font/bootstrap-icons.min.css">
        <div class="row">
            <div class="col-lg-12">
                <h2 class="text-center my-4">RIWAYAT KUNJUNGAN</h2>
                <nuxt-link to="/">
                <i class="bi bi-arrow-left"></i>
                </nuxt-link>
                <div class="my-3">
                    <form @submit.prevent="getpengunjung">
                        <input v-model="keyword" type="search" class="form-control rounded-5" placeholder="Filter...">
                    </form>
                    <div class="my-3 text-muted">menampilkan 1 dari 1</div>
                    <table class="table">
                        <thead>
                            <tr>
                                <td>No</td>
                                <td>NAMA</td>
                                <td>KEANGGOTAAN</td>
                                <td>WAKTU</td>
                                <td>KEPERLUAN</td>
                            </tr>
                        </thead>
                        <tbody>
                            <tr v-for="(visitor,i) in visitors" :key="i">
                                <td>{{ i+1 }}.</td>
                                <td>{{ visitor.nama}}</td>
                                <td>{{ visitor.keanggotaan.nama}}</td>
                                <td>{{ visitor.tanggal }},{{ visitor.waktu}}</td>
                                <td>{{ visitor.keperluan.nama}}</td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
const supabase = useSupabaseClient()

const visitors = ref([])

const getPengunjung = async () => {
    const {data, error} = await supabase.from('pengunjung').select('*, keanggotaan(*), keperluan(*)')
    if(data) visitors.value = data
}
onMounted(()=> {
    getPengunjung()
})

</script>

<style scoped>
i{
    color: black;
    font-size: 2em;
}
</style>