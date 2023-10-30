<script setup>
import { ref, onMounted, onUnmounted } from "vue";

const currentTime = ref("");

const updateTime = () => {
	const now = new Date();
	currentTime.value =
		now.getHours().toString().padStart(2, "0") +
		":" +
		now.getMinutes().toString().padStart(2, "0") +
		":" +
		now.getSeconds().toString().padStart(2, "0");
};

onMounted(() => {
	updateTime();
	const interval = setInterval(updateTime, 1000);
	onUnmounted(() => {
		clearInterval(interval);
	});
});
</script>

<template>
	<section id="TitleSection">
		<video
			class="title-video pc-only"
			preload="metadata"
			loop
			muted
			playsinline
			autoplay
			poster="/header-video-poster.jpg"
		>
			<source src="/header-video.mp4" type="video/mp4" />
		</video>
		<div class="title-top-text-wrapper">
			<div class="box-deco pc-only">
				<p class="text1">
					<span>RUNNING</span> <span>ON</span> <span>A</span>
					<span>FULL-EXCEL</span> <span>CIRCUIT</span>
					<span>THE</span> <span>NEW</span> <span>ENGINE</span>
					<span>OF</span> <span>CHEIL</span> <span>WORLDWIDE.</span>
					<span>IT'S</span> <span>GOING</span> <span>TO</span>
					<span>MAKE</span>
				</p>
				<p class="text2">
					<span>THE</span> <span>HEART</span> <span>OF</span>
					<span>DIGITAL</span> <span>CREATIVITY</span>
					<span>EXPLODE.</span> <span>WE</span> <span>ARE</span>
					<span>CYLNDR</span> <span>SEOUL</span>
				</p>
			</div>
		</div>
		<div class="title-text-wrapper">
			<h1>CYLNDR.</h1>
			<h2>
				(47° 45’ 00” N 126° 58’ 41” E)
				&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; SEOUL
			</h2>
		</div>
		<div class="title-bottom-text-wrapper">
			<p>Worldwide</p>
			<p>&#169;2023</p>
			<p>{{ currentTime }}</p>
		</div>
	</section>
</template>

<style>
@import url("https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700&display=swap");

body {
	background-color: black;
	color: white;
	font-family: "Roboto", sans-serif;
}

.box-deco {
	letter-spacing: -0.03em;
	color: #555;
	font-family: Selecta, sans-serif;
	font-size: 1.6rem;
	font-weight: 300;
	line-height: 1;
	position: absolute;
	top: 30px;
	left: 0;
	right: 0;
}

.box-deco > p {
	flex-direction: row;
	justify-content: space-between;
	align-items: flex-start;
	padding: 0 30px;
	display: flex;
	font-size: calc(5px + 0.45vw);
	margin: 0;
}

.title-text-wrapper h1 {
	font-family: sans-serif;
	font-size: 260px;
	margin: 0;
	line-height: 1;
	text-align: center;
	font-variant: all-small-caps;
	letter-spacing: -6px;
}

.title-text-wrapper h2 {
	font-size: 26px;
	font-weight: 500;
	text-align: center;
	margin: 0;
	line-height: 1;
}

.title-bottom-text-wrapper {
	display: flex;
	justify-content: space-between;
	padding: 0 20px;
	margin-top: 49vh;
}

.title-bottom-text-wrapper > p {
	font-size: 26px;
	text-transform: uppercase;
	font-weight: 500;
}

.title-video {
	border-radius: 50px;
	width: 100%;
	position: absolute;
	top: 200px;
	left: 0;
	z-index: -1;
	padding: 0 10px;
	box-sizing: border-box;
}
</style>
