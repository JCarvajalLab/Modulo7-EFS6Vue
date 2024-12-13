<template>
<ItemsNavbar></ItemsNavbar>
<v-main class="home">
    <div class="background-blur"></div>
    <div class="table-container">
        <h2 class="table-title">Héroes</h2> <!-- Título de la tabla -->
        <div class="filter-icons">
            <i class="fas fa-shield-alt" title="Tanque" @click="filterByTank"></i>
            <i class="fas fa-crosshairs" title="Asesino a distancia" @click="filterByRangedAssassin"></i>
            <i class="fas fa-plus" title="Sanador" @click="filterByHealer"></i>
            <i class="fas fa-sword" title="Guerrero" @click="filterByWarrior"></i>
            <i class="fas fa-user-secret" title="Asesino" @click="filterByAssassin"></i>
            <i class="fas fa-hand-paper" title="Apoyo" @click="filterBySupport"></i>
        </div>
        <v-table class="tablaHeroes" theme="dark">
            <thead>
                <tr>
                    <th class="text-left">Imagen</th>
                    <th class="text-left">Heroes</th>
                    <th class="text-left">Nombre</th>
                    <th class="text-left">Funcion</th>
                    <th class="text-left">Titulo</th>
                    <th class="text-left">Ataque</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="item in desserts" :key="item.name">
                    <td><img :src="item.image" alt="Hero Image" style="width: 200px; height: auto;" /></td>
                    <td>{{ item.name }}</td>
                    <td>{{ item.function }}</td>
                    <td>{{ item.title }}</td>
                    <td>{{ item.attack }}</td>
                </tr>
            </tbody>
        </v-table>
    </div>
</v-main>

<ItemsFooter></ItemsFooter>
</template>

<script>
import ItemsNavbar from '../components/ItemsNavbar.vue';
import ItemsFooter from '../components/ItemsFooter.vue';

export default {
    name: 'HeroesView',
    components: {
        ItemsNavbar,
        ItemsFooter
    },
    data() {
        return {
            desserts: [{
                    name: 'Artanis',
                    function: 'Agresor',
                    title: 'Jerarca de los Daelaam',
                    attack: 111,
                    image: 'https://static.heroesofthestorm.com/heroes/yrel/skins/light-of-hope-800.jpg'
                },
                {
                    name: 'D.Va',
                    function: 'Guerrero',
                    title: 'Piloto de MEKA',
                    attack: 22,
                    image: 'https://static.heroesofthestorm.com/heroes/dva/skins/meka-pilot-800.jpg'
                },
                {
                    name: 'Ragnaros',
                    function: 'Agresor',
                    title: 'El señor del fuego',
                    attack: 180,
                    image: 'https://static.heroesofthestorm.com/heroes/ragnaros/skins/the-firelord-800.jpg'
                },
                {
                    name: 'Yrel',
                    function: 'Guerrero',
                    title: 'Luz de la esperanza',
                    attack: 155,
                    image: 'https://static.heroesofthestorm.com/heroes/yrel/skins/light-of-hope-800.jpg'
                },
                {
                    name: 'Ana',
                    function: 'Sanadora',
                    title: 'Francotiradora veterana',
                    attack: 30,
                    image: 'https://static.heroesofthestorm.com/heroes/ana/skins/veteran-sniper-800.jpg'
                },
                {
                    name: 'Auriel',
                    function: 'Sanadora',
                    title: 'Arcángel de la esperanza',
                    attack: 64,
                    image: 'https://static.heroesofthestorm.com/heroes/ana/skins/veteran-sniper-800.jpg'
                },
                {
                    name: 'Malfurion',
                    function: 'Sanadora',
                    title: 'Archidruida',
                    attack: 60,
                    image: 'https://static.heroesofthestorm.com/heroes/malfurion/skins/archdruid-800.jpg'
                },
                {
                    name: 'Arthas',
                    function: 'Tanque',
                    title: 'El rey Exánime',
                    attack: 95,
                    image: 'https://static.heroesofthestorm.com/heroes/arthas/skins/the-lich-king-800.jpg'
                },
                {
                    name: 'Johanna',
                    function: 'Tanque',
                    title: 'Cruzada de Zakarum',
                    attack: 99,
                    image: 'https://static.heroesofthestorm.com/heroes/johanna/skins/crusader-of-zakarum-800.jpg'
                },
                {
                    name: 'Muradin',
                    function: 'Tanque',
                    title: 'Rey de la montaña',
                    attack: 88,
                    image: 'https://static.heroesofthestorm.com/heroes/muradin/skins/mountain-king-800.jpg'
                },
                {
                    name: 'Illidan',
                    function: 'Asesino',
                    title: 'El traidor',
                    attack: 87,
                    image: 'https://static.heroesofthestorm.com/heroes/illidan/skins/the-betrayer-800.jpg'
                },
                {
                    name: 'Maiev',
                    function: 'Asesino',
                    title: 'La celadora',
                    attack: 145,
                    image: 'https://static.heroesofthestorm.com/heroes/maiev/skins/the-warden-800.jpg'
                },
                {
                    name: 'Zeratul',
                    function: 'Asesino',
                    title: 'Prelado tétrico',
                    attack: 131,
                    image: 'https://static.heroesofthestorm.com/heroes/zeratul/skins/dark-prelate-800.jpg'
                },
                {
                    name: 'Abathur',
                    function: 'Apoyo',
                    title: 'Maestro de evolución',
                    attack: 27,
                    image: 'https://static.heroesofthestorm.com/heroes/abathur/skins/evolution-master-800.jpg'
                },
                {
                    name: 'Medivh',
                    function: 'Apoyo',
                    title: 'El último guardián',
                    attack: 83,
                    image: 'https://www.hellofriki.com/wp-content/uploads/2016/05/medivh.jpg'
                },
                {
                    name: 'Zarya',
                    function: 'Apoyo',
                    title: 'Defensora de Rusia',
                    attack: 22,
                    image: 'https://static.heroesofthestorm.com/heroes/zarya/skins/defender-of-russia-800.jpg'
                },
                {
                    name: 'Nazeebo',
                    function: 'Asesino a distancia',
                    title: 'Médico brujo',
                    attack: 92,
                    image: 'https://static.heroesofthestorm.com/heroes/nazeebo/skins/heretic-witch-doctor-800.jpg'
                },
                {
                    name: 'Genji',
                    function: 'Asesino a distancia',
                    title: 'Ninja cibernético',
                    attack: 44,
                    image: 'https://static.heroesofthestorm.com/heroes/genji/skins/cybernetic-ninja-800.jpg'
                },
                {
                    name: 'Zagara',
                    function: 'Asesino a distancia',
                    title: 'Madre de la prole del enjambre',
                    attack: 85,
                    image: 'https://static.heroesofthestorm.com/heroes/zagara/skins/broodmother-of-the-swarm-800.jpg'
                }
                // Agrega más héroes aquí
            ]
        };
    }
};
</script>

<style>
.home {
    position: relative;
    /* Asegúrate de que el contenedor principal tenga posición relativa */
    min-height: calc(93vh - 64px);
}

.background-blur {
    position: absolute;
    /* Posiciona el fondo de manera absoluta */
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: url('https://blz-contentstack-images.akamaized.net/v3/assets/blt0e00eb71333df64e/blt03542249d3e68c2a/65bc49d6529b719b244a1436/game_features_1.webp') no-repeat center center fixed;
    background-size: cover;
    /* Asegúrate de que la imagen cubra todo el fondo */
    filter: blur(8px);
    /* Aplica el desenfoque solo a este div */
    z-index: 1;
    /* Asegúrate de que esté detrás de la tabla */
}

.table-container {
    max-height: 60vh;
    /* Establece la altura máxima del contenedor */
    overflow-y: auto;
    /* Habilita el desplazamiento vertical */
    margin: 20px 50px;
    /* Margen superior e inferior y centrado */
    z-index: 2;
    /* Asegúrate de que esté por encima del fondo difuminado */
    position: relative;
    /* Asegúrate de que tenga posición relativa */
}

.table-title {
    color: white;
    /*agrandar la letra*/
    font-size: 40px;
    margin-bottom: 10px;
    /* Espacio entre el título y los iconos */
}

.filter-icons i {
    font-size: 35px;
    /* Tamaño de los iconos */
    margin: 5px;
    /* Espacio entre los iconos */
    cursor: pointer;
    /* Cambia el cursor al pasar sobre los iconos */
    transition: color 0.3s;
    /* Transición suave para el color */
    color: white;
    margin-bottom: 20px;
}

.filter-icons i:hover {
    color: #ffcc00;
    /* Cambia el color al pasar el mouse */
}

.tablaHeroes {
    width: 100%;
    /* Asegúrate de que la tabla ocupe el 100% del ancho disponible */
    border-collapse: collapse;
    /* Colapsa los bordes de la tabla */
    margin: 0;
    /* Elimina el margen de la tabla */
    padding: 0;
    /* Elimina el padding de la tabla */
}
</style>
