<script lang="ts">
	export let projectName;
	export let projectDescription;
	export let technologies;
	export let projectimg;
	export let projectimgalt;
	export let projectGithub;
	export let projectLink;
</script>

<!-- Array<string> -->
<div class="area">
	<p class="title">{projectName}</p>
	<div class="links">
		{#if projectLink}
			<div>
				<a class="single-link" target="_blank" href={projectLink}>
					<svg
						width="15"
						height="15"
						xmlns="http://www.w3.org/2000/svg"
						fill-rule="evenodd"
						clip-rule="evenodd"
					>
						<path
							d="M12.02 0c6.614.011 11.98 5.383 11.98 12 0 6.623-5.376 12-12 12-6.623 0-12-5.377-12-12 0-6.617 5.367-11.989 11.981-12h.039zm3.694 16h-7.427c.639 4.266 2.242 7 3.713 7 1.472 0 3.075-2.734 3.714-7m6.535 0h-5.523c-.426 2.985-1.321 5.402-2.485 6.771 3.669-.76 6.671-3.35 8.008-6.771m-14.974 0h-5.524c1.338 3.421 4.34 6.011 8.009 6.771-1.164-1.369-2.059-3.786-2.485-6.771m-.123-7h-5.736c-.331 1.166-.741 3.389 0 6h5.736c-.188-1.814-.215-3.925 0-6m8.691 0h-7.685c-.195 1.8-.225 3.927 0 6h7.685c.196-1.811.224-3.93 0-6m6.742 0h-5.736c.062.592.308 3.019 0 6h5.736c.741-2.612.331-4.835 0-6m-12.825-7.771c-3.669.76-6.671 3.35-8.009 6.771h5.524c.426-2.985 1.321-5.403 2.485-6.771m5.954 6.771c-.639-4.266-2.242-7-3.714-7-1.471 0-3.074 2.734-3.713 7h7.427zm-1.473-6.771c1.164 1.368 2.059 3.786 2.485 6.771h5.523c-1.337-3.421-4.339-6.011-8.008-6.771"
						/>
					</svg>
					Live Demo
				</a>
			</div>
		{/if}
		{#if projectGithub}
			<div>
				<a class="single-link" href={projectGithub} target="_blank">
					<svg xmlns="http://www.w3.org/2000/svg" width="15" height="15" viewBox="0 0 24 24">
						<path
							d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"
						/>
					</svg>
					GitHub Repo
				</a>
			</div>
		{/if}
	</div>
	<div class="project">
		<div>
			<p class="description">{projectDescription}</p>

			<div class="technologies">
				{#each technologies as technology}
					<p class="oneTech">{technology}</p>
				{/each}
			</div>
		</div>
		<img alt={projectimgalt} src={projectimg} />
	</div>
</div>

<style>
	a {
		color: black;
		text-decoration: none;
	}
	.single-link {
		border-radius: 5px;
		background-color: #b3c7f7;
		padding: 15px;
		margin: 0 40px;
		box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.2);
	}
	.area {
		background-color: white;
		max-width: 70vw;
		height: 50%;
		padding: 1rem;
		box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.2);
	}
	.links {
		display: flex;
		justify-content: center; /* Horizontally center the items */
		max-width: 75%;
		margin: 0 auto;
		padding-bottom: 20px;
	}
	.project {
		display: flex;
	}
	.description {
		padding-left: 10%;
		padding-right: 10%;
		color: rgb(78, 78, 78);
		font-size: larger;
	}
	.technologies {
		display: flex;
		justify-content: space-around;
		padding-left: 10%;
		padding-right: 10%;
		flex-wrap: wrap;
		max-width: 70%;
		margin: auto;
	}
	.oneTech {
		background-color: #005286;
		padding: 2% 20px;
		border-radius: 5%;
		color: #f0f8ff;
		margin-top: 0;
		/* font-size: smaller; */
	}
	img {
		/* max-height: 200px; */
		padding-right: 20px;
		padding-top: 40px;
		padding-bottom: 20px;
		width: 400px;
		max-height: 200px;
		/* height: auto; */
		/* object-fit: contain; */
	}
	.title {
		flex: 1;
		font-size: x-large;
	}
	@media screen and (min-width: 640px) and (max-width: 1275px) {
		.project {
			flex-direction: column-reverse;
			align-items: center; /* Center items horizontally */
		}

		img {
			max-height: 400px;
			max-width: 200px;
			padding-right: 0;
			margin: auto; /* Center the image horizontally */
		}
		.single-link {
			display: block;
			margin: 10px 0; /* Add margin between the buttons */
			text-align: center; /* Center the text horizontally */
			line-height: 2.5;
		}
		.area {
			/* width: 100%; */
			height: 50%;
			padding: 0 10px;
			padding-top: 20px;
			max-width: 80vw;
			/* margin: 0 auto; */
		}
		.links {
			padding-left: 0;
			padding-right: 0;
			flex-direction: column;
		}
		/* .project {
			flex-direction: column-reverse;
		}
		img {
			max-height: 400px;
			padding-right: 0;
		} */
		.technologies {
			flex-wrap: wrap;
			padding: 5px 20px;
		}
	}

	@media screen and (max-width: 640px) {
		.single-link {
			display: block;
			margin: 10px 0; /* Add margin between the buttons */
			text-align: center; /* Center the text horizontally */
			line-height: 2.5;
		}
		.area {
			/* width: 100%; */
			max-width: 100%;
			height: 70%;
			padding: 0 10px;
			padding-top: 20px;
			/* margin: 0 auto; */
		}
		.links {
			padding-left: 0;
			padding-right: 0;
			flex-direction: column;
		}
		svg {
			padding-top: 10px;
		}
		.project {
			flex-direction: column-reverse;
			align-items: center; /* Center items horizontally */
		}

		img {
			max-height: 400px;
			padding-right: 0;
			margin: auto; /* Center the image horizontally */
		}
		/* .project {
			flex-direction: column-reverse;
		}
		img {
			max-height: 400px;
			padding-right: 0;
		} */
		.technologies {
			flex-wrap: wrap;
			padding: 5px 20px;
		}
		.oneTech {
			/* font-size: smaller; */
		}
	}

	@media screen and (min-width: 320px) and (max-width: 639px) {
		.single-link {
			display: block;
			margin: 10px 0; /* Add margin between the buttons */
			text-align: center; /* Center the text horizontally */
			line-height: 2.5;
		}
		.area {
			/* width: 100%; */
			max-width: 100%;
			height: 70%;
			padding: 0 10px;
			padding-top: 20px;
			/* margin: 0 auto; */
		}
		.links {
			padding-left: 0;
			padding-right: 0;
			flex-direction: column;
		}
		svg {
			padding-top: 10px;
		}
		.project {
			flex-direction: column-reverse;
			align-items: center; /* Center items horizontally */
		}

		img {
			/* max-height: 400px; */
			max-width: 300px;

			padding-right: 0;
			margin: auto; /* Center the image horizontally */
		}
		/* .project {
			flex-direction: column-reverse;
		}
		img {
			max-height: 400px;
			padding-right: 0;
		} */
		.technologies {
			flex-wrap: wrap;
			padding: 5px 20px;
		}
		.oneTech {
			/* font-size: smaller; */
		}
	}
</style>
