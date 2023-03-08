<script context="module">
	import FeatureCard from '../components/FeatureCard.svelte';
	import LatestPosts from '../components/LatestPosts.svelte';
	import {
		SITE_URL,
		REPO_URL,
		SITE_TITLE,
		SITE_DESCRIPTION,
		DEFAULT_OG_IMAGE,
		MY_TWITTER_HANDLE
	} from '$lib/siteConfig';
	export const prerender = true; // Since index page is most common page, we should prerender this to improve load time.
</script>

<svelte:head>
	<title>{SITE_TITLE}</title>
	<link rel="canonical" href={SITE_URL} />
	<link rel="alternate" type="application/rss+xml" href={SITE_URL + '/rss.xml'} />
	<meta property="og:url" content={SITE_URL} />
	<meta property="og:type" content="article" />
	<meta property="og:title" content={SITE_TITLE} />
	<meta name="Description" content={SITE_DESCRIPTION} />
	<meta property="og:description" content={SITE_DESCRIPTION} />
	<meta property="og:image" content={DEFAULT_OG_IMAGE} />
	<meta name="twitter:card" content="summary" />
	<meta name="twitter:creator" content={'@' + MY_TWITTER_HANDLE} />
	<meta name="twitter:title" content={SITE_TITLE} />
	<meta name="twitter:description" content={SITE_DESCRIPTION} />
	<meta name="twitter:image" content={DEFAULT_OG_IMAGE} />
</svelte:head>

<div
	class="mx-auto flex max-w-4xl flex-col items-start justify-center border-zinc-200 px-4 pb-16 dark:border-yellow-700 sm:px-8"
>
	<div class="flex flex-col-reverse items-start sm:flex-row">
		<div class="flex flex-col pr-8">
			
			<h1 class="mb-3 text-3xl font-bold tracking-tight text-black dark:text-blue-500 md:text-5xl">
				Lukas Winn
			</h1>
			<h2 class="mb-4 text-gray-700 dark:text-gray-200">
				My little Corner of the Internet to share my knowledge and opinions on tech related content with a focus on VMware, Coding and other tech areas.
				<br />
				<br /> Currently working on: <span class="font-semibold">
				Learning about Sveltekit and how I can apply this to my blog...</span>
			</h2>
			<br />
			<br />
		</div>
		<!-- <div
				class="w-[80px] h-[80px] rounded-full sm:w-[176px] sm:h-[136px] relative mb-8 sm:mb-0 mr-auto bg-cyan-300 bg-opacity-25"
			/> -->
		</div>
		<section class="w-full mb-16">
		<h3 class="mb-6 text-2xl font-bold tracking-tight text-black dark:text-white md:text-4xl">
			Featured Posts
		</h3>
		<div class="flex flex-col gap-6 md:flex-row">
			<FeatureCard title="Welcome to swyxkit 2022!" href="/welcome" stringData="Jan 2022" />
			<FeatureCard
				title="Moving to a GitHub CMS"
				href="/moving-to-a-github-cms"
				stringData="Jan 2022"
			/>
			<FeatureCard title="HTML Ipsum demo" href="/moo" stringData="Jan 2022" />
		</div>
	</section>

	<!-- <LatestPosts {items} /> -->

</div>