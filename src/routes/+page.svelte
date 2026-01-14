<script>

const equipos = 'https://www.thesportsdb.com/api/v1/json/123/search_all_teams.php?l=Spanish_tercera_federacion_group_1';


const fetchEquipos = async () =>{

    const response = await fetch(equipos);
    const data = await response.json();

    return await data.teams;
 };


 let promise = fetchEquipos();



</script>

<section class="teams">
  <div class="teams__tittle">
    <h2 class="teams__h2">ESCOLLE O TEU CLUBE

    </h2>
  </div>

  <div class="teams__cards">

{#await promise}

    <p>Cargando equipos ...</p>
{:then equiposLiga} 
    
{#each equiposLiga as team }
    <!-- inicia card -->
     <a class="teams__a" href="/{team.idTeam}">
  <div class="teams__container">
    <div class="teams__card">
      <div class="teams__badge">
        <img class="teams__img" src={team.strBadge} alt={team.strTeam} />
      </div>
    </div>
      <div class="teams__name">
        <p>{team.strTeam}</p>
      </div>
<!-- finaliza cada card -->
  </div>
  </a>
{/each}

  
  {/await}
    </div>
    <button class="teams__button">
        SELECCIONA UN CLUBE
    </button>
</section>

<style>
.teams{
padding: 1.1rem;
}

.teams__tittle{
width: 100%;
}

.teams__h2{
    text-align: center;
    font-size: 1.4rem;
}

.teams__cards{
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    justify-content: center;
}

.teams__container{
    display: flex;
    gap: 1px;
    flex-direction: column;
    align-items: center;
    width: 94px;
}


.teams__card{

    width: 99px;
    height: 99px;
    display: flex;
    justify-content: center;
    align-items: center;
}

.teams__badge{
    border-radius: 10px;
    height: 30px;
    width: 30px;
    display: flex;
    justify-content: center;
    align-items: center;

}

.teams__img{
    max-width: 75px;
}

.teams__cards{
padding: 1rem 0px;
}

.teams__button{
    width: 100%;
    font-size: 1rem;
    padding: 1rem;
    border-radius: 8px;


}

.teams__name{
    text-align: center;
    height: 50px;
    color: rgb(187, 187, 187);
}

</style>
