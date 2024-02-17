<script>
export default{
    
    data(){
        return{
            noControl: '',
            nombreComp: '',
            edad: 0,
            semestre: 0,
            carrera: '',
            especialidad: null,
            actExtra: null,
            usuarios: []
        }
    },
    methods: {
        añadirAlumno(){
            var data = {
                noControl: this.noControl,
                nombreComp: this.nombreComp,
                edad: this.edad,
                semestre: this.semestre,
                carrera: this.carrera,
                especialidad: this.especialidad,
                actExtra: this.actExtra
            };
            this.usuarios.push(data);
            this.noControl = '';
            this.nombreComp = '';
            this.edad = 0;
            this.semestre = 0;
            this.carrera = '';
            this.especialidad = null;
            this.actExtra = null;
        }
    }
}
</script>

<template>
    <form @submit.prevent="añadirAlumno">
        <h1 class="text-2x1 font-bold">Formulario</h1>
        <div class="flex flex-col my-2">
                <label class="col-form-label">No. Control</label>
                <input type="text" class="form-control" v-model="noControl">
            </div>
            <div class="flex flex-col my-2">
                <label class="col-form-label">Nombre Completo</label>
                <input type="text" class="form-control" v-model="nombreComp">
            </div>
            <div class="flex flex-col my-2">
                <label class="col-form-label">Edad</label>
                <input type="number" class="form-control" v-model="edad">
            </div>
            <div class="flex flex-col my-2">
                <label class="col-form-label">Semestre</label>
                <input type="number" class="form-control" v-model="semestre">
            </div>
            <div class="flex flex-col my-2">
                <label class="col-form-label">Carrera</label>
                <select v-model="carrera" class="form-select" >
                    <option selected>Seleciona...</option>
                    <option value="ISC">ISC</option>
                    <option value="IM">IM</option>
                    <option value="IIA">IIA</option>
                    <option value="CP">CP</option>
                    <option value="LA">LA</option>
                </select>
            </div>
            <div class="flex flex-col my-2 terms">
                <h4>Especialidades</h4>
                <input value="Ingeniería de Datos" class="form-check-input" type="radio" v-model="especialidad">
                <label class="form-check-label"> Ingeniería de Datos </label>
                <br>
                <input value="Redes" class="form-check-input" type="radio" v-model="especialidad">
                <label class="form-check-label"> Redes </label>
                <br>
                <input value="Devops" class="form-check-input" type="radio" v-model="especialidad">
                <label class="form-check-label"> Devops </label>
            </div>
            <div class="flex flex-col my-2 terms">
                <h4>Actividades Extraescolares</h4>
                <input value="Deportes" class="form-check-input" type="radio" v-model="actExtra">
                <label class="form-check-label"> Deportes </label>
                <br>
                <input value="Banda de Guerra" class="form-check-input" type="radio" v-model="actExtra">
                <label class="form-check-label"> Banda de Guerra </label>
                <br>
                <input value="Danza" class="form-check-input" type="radio" v-model="actExtra">
                <label class="form-check-label"> Danza </label>
            </div>
            <button class="mt-4 border bg-primary bg-gradient inline px-3 py-1 rounded text-white"
            type="submit">
                Agregar
            </button>
    </form>
    <div class="row">
        <div class="col m12">
            <table class="table borderedd striped">
                <thead>
                    <tr class="table-primary">
                        <th>No. Control</th>
                        <th>Nombre Completo</th>
                        <th>Edad</th>
                        <th>Semestre</th>
                        <th>Carrera</th>
                        <th>Especialidad</th>
                        <th>Act. Extraescolar</th>
                    </tr>
                </thead>
                <tbody>
                    
                    <tr v-for="usuario in usuarios" v-bind:key="usuario">
                        <td>{{ usuario.noControl }}</td>
                        <td>{{ usuario.nombreComp }}</td>
                        <td>{{ usuario.edad }}</td>
                        <td>{{ usuario.semestre }}</td>
                        <td>{{ usuario.carrera }}</td>
                        <td>{{ usuario.especialidad }}</td>
                        <td>{{ usuario.actExtra }}</td>
                        </tr>    
                </tbody>
            </table>
        </div>
    </div>
</template>

<style>
    form{
        max-width: 420px;
        margin: 30px auto;
        background: #F5D5E8;
        text-align: left;
        padding: 40px;
        border-radius: 10px;
    }
</style>