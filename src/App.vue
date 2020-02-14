<template>
 	<div class="container">
 		<div class="row justify-content-center">
 			<h1>Math Quizer</h1>
 		</div>
 		<hr class="col-md-8">
 		<div class="row justify-content-center">
 			<transition
 				appear
 				enter-active-class="animated flipInX"
 				leave-active-class="animated flipOutX"
 				mode="out-in"	
 				>
 				<component 
	 				:is="selectedComponent" 
	 				@answered="answered($event)" 
	 				@confirmed="selectedComponent = 'app-question'"></component>
 			</transition>
 		</div>
 	</div>
</template>

<script>
	import Question from './components/quiz/Question.vue';
	import Answer from './components/quiz/Answer.vue';

	export default {
		data() {
			return {
				selectedComponent: 'app-question'
			}
		},
		methods: {
        	answered(isCorrect) {
            	if (isCorrect) {
                	this.selectedComponent = 'app-answer';
            	} else {
                	this.selectedComponent = 'app-question';
                	alert('Wrong, try again!');
            	}
        	}
        },
		components: {
			'app-question': Question,
			'app-answer': Answer
		}
	}
</script>

