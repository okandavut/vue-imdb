<template>
	<div class="new"> 
	<div  v-bind="films" v-if="films.Error!='Movie not found!'" >	
		<img :src="films.Poster"></li>
		<h4>Film name : {{films.Title}}</h4>
		<h4>Film IMDB Score : {{films.imdbRating}} / 10</h4>
		<h4>Film IMDB Votes : {{films.imdbVotes}}</h4>
		<h4>Film Genre : {{films.Genre}}</h4>
		<h4>Film Director : {{films.Director}}</h4>
		<h4>Film Actors : {{films.Actors}}</h4>
		<h4>Film Production : {{films.Production}}</h4>
		<h4>Film Language : {{films.Language}}</h4>
		<h4>Film Awards : {{films.Awards}}</h4>
		<h4>Film Short Summary : {{films.Plot}}</h4>
		

	</div>
	<div  v-bind="films" v-if="films.Error=='Movie not found!'" >
				<h4>{{films.Error}}</h4>

	</div>
	</div>
</template>

<script>
	export default{
	props:['films']
} 

</script>

<style> 
.new img{
	float:left;
	margin-right:40px;

}
.new h4{
	margin-top:23px;
}
</style>