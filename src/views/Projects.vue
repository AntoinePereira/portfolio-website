<template>
  <div class="about">
    <h1>This is an about page</h1>
    <p>{{ $t('projects.test') }}</p>
    <div class="projectThumbnail">
			<div class="apercuResto">	
				<img src="@/assets/ohmyfood.png" class="" alt="">
			</div>
			<div class="projectThumbnail--tag">
						<span><strong>The Full Palette</strong><br>New York</span>
						
					</div>
				</div>
  </div>
</template>

<style lang="scss" scoped>
@mixin tagstyle{
	background-color: grey;
	border-radius: 1em;
	box-shadow: 0.5em 0.5em 0.5em #eaeaea;
	font-size: 0.8em;
	margin-bottom: 1.3em;
	height: 4em;
}
</style> 