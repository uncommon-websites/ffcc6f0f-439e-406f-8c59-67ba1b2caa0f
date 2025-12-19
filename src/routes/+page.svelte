<script lang="ts">
	// Icons
	const icons = {
		logo: `<svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" class="w-6 h-6 text-blue-500"><path d="M12 2L14.5 9H22L16 13.5L18.5 21L12 16.5L5.5 21L8 13.5L2 9H9.5L12 2Z" fill="currentColor" stroke="currentColor" stroke-width="2" stroke-linejoin="round"/></svg>`, // Placeholder for flower
		clock: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><circle cx="12" cy="12" r="10"/><polyline points="12 6 12 12 16 14"/></svg>`,
		arrowRight: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><line x1="5" y1="12" x2="19" y2="12"/><polyline points="12 5 19 12 12 19"/></svg>`,
		reflection: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M2 3h6a4 4 0 0 1 4 4v14a3 3 0 0 0-3-3H2z"/><path d="M22 3h-6a4 4 0 0 0-4 4v14a3 3 0 0 1 3-3h7z"/></svg>`,
		productivity: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><polygon points="13 2 3 14 12 14 11 22 21 10 12 10 13 2"/></svg>`,
		memory: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M9.5 2A2.5 2.5 0 0 1 12 4.5v15a2.5 2.5 0 0 1-4.96.44 2.5 2.5 0 0 1-2.96-3.08 3 3 0 0 1-.34-5.58 2.5 2.5 0 0 1 1.32-4.24 2.5 2.5 0 0 1 1.98-3A2.5 2.5 0 0 1 9.5 2Z"/><path d="M14.5 2A2.5 2.5 0 0 0 12 4.5v15a2.5 2.5 0 0 0 4.96.44 2.5 2.5 0 0 0 2.96-3.08 3 3 0 0 0 .34-5.58 2.5 2.5 0 0 0-1.32-4.24 2.5 2.5 0 0 0-1.98-3A2.5 2.5 0 0 0 14.5 2Z"/></svg>`,
		clarity: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M12 2v4"/><path d="M12 18v4"/><path d="M4.93 4.93l2.83 2.83"/><path d="M16.24 16.24l2.83 2.83"/><path d="M2 12h4"/><path d="M18 12h4"/><path d="M4.93 19.07l2.83-2.83"/><path d="M16.24 7.76l2.83-2.83"/></svg>`,
		speedometer: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5"><path d="M22 12A10 10 0 0 0 12 2v10z"/></svg>`, // Simplified
		shield: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/></svg>`,
		sparkles: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5"><path d="m12 3-1.912 5.813a2 2 0 0 1-1.275 1.275L3 12l5.813 1.912a2 2 0 0 1 1.275 1.275L12 21l1.912-5.813a2 2 0 0 1 1.275-1.275L21 12l-5.813-1.912a2 2 0 0 1-1.275-1.275L12 3Z"/></svg>`,
		soundwave: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5"><path d="M12 2v20"/><path d="M16 6v12"/><path d="M20 10v4"/><path d="M8 6v12"/><path d="M4 10v4"/></svg>`,
		plus: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5"><line x1="12" y1="5" x2="12" y2="19"/><line x1="5" y1="12" x2="19" y2="12"/></svg>`,
		check: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><polyline points="20 6 9 17 4 12"/></svg>`,
		calendar: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><rect x="3" y="4" width="18" height="18" rx="2" ry="2"/><line x1="16" y1="2" x2="16" y2="6"/><line x1="8" y1="2" x2="8" y2="6"/><line x1="3" y1="10" x2="21" y2="10"/></svg>`,
		repeat: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><polyline points="17 1 21 5 17 9"/><path d="M3 11V9a4 4 0 0 1 4-4h14"/><polyline points="7 23 3 19 7 15"/><path d="M21 13v2a4 4 0 0 1-4 4H3"/></svg>`,
		search: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><circle cx="11" cy="11" r="8"/><line x1="21" y1="21" x2="16.65" y2="16.65"/></svg>`,
		camera: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M23 19a2 2 0 0 1-2 2H3a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h4l2-3h6l2 3h4a2 2 0 0 1 2 2z"/><circle cx="12" cy="13" r="4"/></svg>`,
		mic: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M12 1a3 3 0 0 0-3 3v8a3 3 0 0 0 6 0V4a3 3 0 0 0-3-3z"/><path d="M19 10v2a7 7 0 0 1-14 0v-2"/><line x1="12" y1="19" x2="12" y2="23"/><line x1="8" y1="23" x2="16" y2="23"/></svg>`,
		download: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"/><polyline points="7 10 12 15 17 10"/><line x1="12" y1="15" x2="12" y2="3"/></svg>`,
		layout: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><rect x="3" y="3" width="18" height="18" rx="2" ry="2"/><line x1="3" y1="9" x2="21" y2="9"/><line x1="9" y1="21" x2="9" y2="9"/></svg>`,
		target: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><circle cx="12" cy="12" r="10"/><circle cx="12" cy="12" r="6"/><circle cx="12" cy="12" r="2"/></svg>`,
		list: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><line x1="8" y1="6" x2="21" y2="6"/><line x1="8" y1="12" x2="21" y2="12"/><line x1="8" y1="18" x2="21" y2="18"/><line x1="3" y1="6" x2="3.01" y2="6"/><line x1="3" y1="12" x2="3.01" y2="12"/><line x1="3" y1="18" x2="3.01" y2="18"/></svg>`,
		link: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"/><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"/></svg>`,
		maximize: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M8 3H5a2 2 0 0 0-2 2v3m18 0V5a2 2 0 0 0-2-2h-3m0 18h3a2 2 0 0 0 2-2v-3M3 16v3a2 2 0 0 0 2 2h3"/></svg>`,
		externalLink: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"/><polyline points="15 3 21 3 21 9"/><line x1="10" y1="14" x2="21" y2="3"/></svg>`,
	};
</script>

<div class="min-h-screen bg-white">
	<!-- Header -->
	<header class="flex items-center justify-between px-6 py-4 max-w-7xl mx-auto">
		<div class="flex items-center gap-3">
			<!-- Logo Icon -->
			<div class="text-gray-900">
				<svg width="38" height="32" viewBox="0 0 152 125" fill="none" xmlns="http://www.w3.org/2000/svg">
					<path d="M143.58 84.2131H151.874L141.028 72.9422C125.504 56.7801 104.026 47.6357 81.4839 47.6357H78.9319H73.4028H70.6382C48.309 47.6357 26.8304 56.7801 11.0937 72.9422L0.248047 84.2131H8.54176C30.871 84.2131 52.3495 75.0688 68.0863 58.9067L76.1674 50.613C71.4889 79.1093 30.871 124.193 30.871 124.193H76.38H121.889C121.889 124.193 81.6965 79.7473 76.5927 51.2509L84.0358 59.1193C99.5599 75.0688 121.038 84.2131 143.58 84.2131Z" fill="currentColor"/>
					<path d="M69.362 31.0482L75.9544 24.2431L82.5469 31.0482C95.3064 44.4457 113.17 51.8888 131.671 51.8888H138.476L129.545 42.5318C116.785 29.1342 98.9216 21.6912 80.4203 21.6912H78.2937H73.6152H71.4886C52.9872 21.6912 35.3365 29.1342 22.3643 42.5318L13.4326 52.1014H20.2377C38.7391 52.1014 56.6024 44.4457 69.362 31.0482Z" fill="currentColor"/>
					<path d="M70.638 7.65573L75.9544 2.12659L81.2709 7.65573C91.6912 18.5013 106.152 24.6685 121.251 24.6685H126.78L119.55 17.0127C109.129 6.16712 94.6684 0 79.5696 0H77.8684H74.0405H72.3392C57.2404 0 42.7796 6.16712 32.3593 17.0127L25.1289 24.6685H30.658C45.7568 24.6685 60.2177 18.5013 70.638 7.65573Z" fill="currentColor"/>
				</svg>
			</div>
			<span class="font-bold text-xl tracking-tight">Asymmetry</span>
		</div>
		<nav class="flex items-center gap-6 text-sm font-medium">
			<a href="#archive" class="text-gray-600 hover:text-gray-900">Archive</a>
			<a href="#subscribe" class="bg-gray-900 px-4 py-2 rounded-lg text-white hover:bg-gray-800 transition-colors">Subscribe</a>
		</nav>
	</header>

	<main>
		<!-- Hero Section -->
		<section class="max-w-4xl mx-auto px-6 pt-12 pb-20 text-center">
			<div class="inline-flex items-center gap-2 text-gray-500 text-sm mb-6">
				{@html icons.clock}
				<span>Weekly • 2-4 min reads</span>
			</div>
			
			<h1 class="text-5xl md:text-6xl font-bold tracking-tight text-gray-900 mb-6 leading-[1.1]">
				Tiny insights that change how you play the game
			</h1>
			
			<p class="text-xl text-gray-600 mb-10 max-w-2xl mx-auto">
				Field notes from experienced builders. Tactical AI engineering insights. No fluff, no news aggregation—just the unsexy details that actually matter.
			</p>

			<div class="flex flex-col sm:flex-row items-center justify-center gap-4 max-w-lg mx-auto mb-16">
				<div class="relative w-full">
					<input 
						type="email" 
						placeholder="Your email address" 
						class="w-full pl-4 pr-12 py-3 rounded-xl border border-gray-200 focus:outline-none focus:ring-2 focus:ring-primary-500/20 focus:border-primary-500 transition-all"
					/>
					<button class="absolute right-2 top-1/2 -translate-y-1/2 p-1.5 text-gray-400 hover:text-primary-600">
						{@html icons.arrowRight}
					</button>
				</div>
				<div class="text-xs text-left text-gray-500 w-full sm:w-auto shrink-0">
					Join 100K+ AI engineers<br>building in production
				</div>
			</div>

			<!-- Hero Image -->
			<div class="relative rounded-2xl border border-gray-200 shadow-2xl bg-white overflow-hidden aspect-[16/9] mb-12">
				<img 
					src="/generated/image-ai-engineer-at-a-startup-working-at-thei-1766168446755-0.webp" 
					alt="AI engineer working at startup" 
					class="w-full h-full object-cover"
				/>
			</div>

			<!-- Bottom Stats -->
			<div class="flex flex-wrap justify-center gap-8 md:gap-12 text-sm font-medium text-gray-700">
				<div class="flex items-center gap-2">
					{@html icons.reflection}
					<span>Field notes</span>
				</div>
				<div class="flex items-center gap-2">
					{@html icons.productivity}
					<span>Lived lessons</span>
				</div>
				<div class="flex items-center gap-2">
					{@html icons.memory}
					<span>Case studies</span>
				</div>
				<div class="flex items-center gap-2">
					{@html icons.clarity}
					<span>Battle-tested frameworks</span>
				</div>
			</div>
		<!-- Why Different Section -->
		<section class="max-w-6xl mx-auto px-6 py-20">
			<h2 class="text-3xl md:text-4xl font-bold text-gray-900 mb-12 max-w-2xl leading-tight">
				Most content is noise. Asymmetry is signal.
			</h2>

			<div class="grid grid-cols-1 md:grid-cols-3 gap-6">
				<!-- Card 1 -->
				<div class="bg-gray-50 p-8 rounded-2xl flex flex-col items-start h-64">
					<div class="mb-auto text-gray-900">
						{@html icons.target}
					</div>
					<div>
						<h3 class="font-bold text-lg mb-2 text-gray-900">Asymmetric insights</h3>
						<p class="text-sm text-gray-600 leading-relaxed">Tiny bets with minimal downside and massive upside. The unsexy details that change everything.</p>
					</div>
				</div>

				<!-- Card 2 -->
				<div class="bg-gray-50 p-8 rounded-2xl flex flex-col items-start h-64">
					<div class="mb-auto text-gray-900">
						{@html icons.productivity}
					</div>
					<div>
						<h3 class="font-bold text-lg mb-2 text-gray-900">Real builder experience</h3>
						<p class="text-sm text-gray-600 leading-relaxed">From founders who've shipped, scaled, and learned the hard way. No theory, just practice.</p>
					</div>
				</div>

				<!-- Card 3 -->
				<div class="bg-gray-50 p-8 rounded-2xl flex flex-col items-start h-64">
					<div class="mb-auto text-gray-900">
						{@html icons.sparkles}
					</div>
					<div>
						<h3 class="font-bold text-lg mb-2 text-gray-900">Production patterns</h3>
						<p class="text-sm text-gray-600 leading-relaxed">Battle-tested frameworks for AI engineering. What actually works when you're shipping.</p>
					</div>
				</div>

				<!-- Card 4 -->
				<div class="bg-gray-50 p-8 rounded-2xl flex flex-col items-start h-64">
					<div class="mb-auto text-gray-900">
						{@html icons.layout}
					</div>
					<div>
						<h3 class="font-bold text-lg mb-2 text-gray-900">Unpolished & authentic</h3>
						<p class="text-sm text-gray-600 leading-relaxed">Raw lessons from the trenches. Ideas that sharpen thinking, not content for content's sake.</p>
					</div>
				</div>

				<!-- Card 5 -->
				<div class="bg-gray-50 p-8 rounded-2xl flex flex-col items-start h-64">
					<div class="mb-auto text-gray-900">
						{@html icons.clock}
					</div>
					<div>
						<h3 class="font-bold text-lg mb-2 text-gray-900">Respectful of time</h3>
						<p class="text-sm text-gray-600 leading-relaxed">2-4 minute reads, weekly. Dense with insight, light on fluff. Get back to building.</p>
					</div>
				</div>

				<!-- Card 6 -->
				<div class="bg-gray-50 p-8 rounded-2xl flex flex-col items-start h-64">
					<div class="mb-auto text-gray-900">
						{@html icons.search}
					</div>
					<div>
						<h3 class="font-bold text-lg mb-2 text-gray-900">No news aggregation</h3>
						<p class="text-sm text-gray-600 leading-relaxed">Not another AI newsletter regurgitating headlines. Tactical insights you can apply today.</p>
					</div>
				</div>
			</div>
		</section>

		<!-- Featured Content Section -->
		<section class="max-w-6xl mx-auto px-6 py-20">
			<div class="mb-16">
				<span class="inline-block bg-primary-100 text-primary-700 px-3 py-1 rounded-full text-xs font-semibold uppercase tracking-wide mb-6">
					Recent field notes
				</span>
				<h2 class="text-4xl md:text-5xl font-bold text-gray-900 mb-6 tracking-tight">
					What you'll get every week
				</h2>
				<p class="text-xl text-gray-600 max-w-2xl leading-relaxed">
					Interviews with top founders, lessons from building in production, and the tactical insights that shift how you think about AI engineering.
				</p>
			</div>

			<div class="grid grid-cols-1 md:grid-cols-2 gap-8 mb-16">
				<!-- Featured Article 1 -->
				<div class="bg-white border border-gray-200 rounded-2xl overflow-hidden hover:shadow-lg transition-shadow">
					<div class="aspect-[3/2] bg-gray-100 overflow-hidden">
						<img 
							src="/generated/image-founder-writing-notes-in-a-notebook-duri-1766168449420-1.webp" 
							alt="Founder taking notes" 
							class="w-full h-full object-cover"
						/>
					</div>
					<div class="p-6">
						<div class="text-xs text-primary-600 font-semibold uppercase tracking-wide mb-2">Nov 10, 2025</div>
						<h3 class="font-bold text-xl mb-3 text-gray-900">No existential thoughts</h3>
						<p class="text-sm text-gray-600 mb-4 leading-relaxed">
							Lessons from a top 1% founder: "I don't think about existential questions. I think about the next thing I need to do to move forward."
						</p>
						<a href="#" class="text-primary-600 hover:text-primary-700 text-sm font-medium inline-flex items-center gap-1">
							Read more {@html icons.arrowRight}
						</a>
					</div>
				</div>

				<!-- Featured Article 2 -->
				<div class="bg-white border border-gray-200 rounded-2xl overflow-hidden hover:shadow-lg transition-shadow">
					<div class="aspect-[3/2] bg-gray-100 overflow-hidden">
						<img 
							src="/generated/image-two-engineers-collaborating-at-a-whitebo-1766168451761-2.webp" 
							alt="Engineers collaborating" 
							class="w-full h-full object-cover"
						/>
					</div>
					<div class="p-6">
						<div class="text-xs text-primary-600 font-semibold uppercase tracking-wide mb-2">Nov 5, 2025</div>
						<h3 class="font-bold text-xl mb-3 text-gray-900">Watch the work</h3>
						<p class="text-sm text-gray-600 mb-4 leading-relaxed">
							How a founder scaled from $1m to $16m ARR in 8 months: "Stop asking users what their problems are and just watch them work."
						</p>
						<a href="#" class="text-primary-600 hover:text-primary-700 text-sm font-medium inline-flex items-center gap-1">
							Read more {@html icons.arrowRight}
						</a>
					</div>
				</div>

				<!-- Featured Article 3 -->
				<div class="bg-white border border-gray-200 rounded-2xl overflow-hidden hover:shadow-lg transition-shadow">
					<div class="p-6">
						<div class="text-xs text-primary-600 font-semibold uppercase tracking-wide mb-2">Sep 22, 2025</div>
						<h3 class="font-bold text-xl mb-3 text-gray-900">Learnings from Arctas, Part I</h3>
						<p class="text-sm text-gray-600 mb-4 leading-relaxed">
							6 lessons from the early stages: Always test hypotheses, focus on revenue creation over time savings, and use the "5 whys" to get to root problems.
						</p>
						<div class="space-y-2 mb-4">
							<div class="flex items-start gap-2 text-xs text-gray-600">
								<span class="text-primary-600 mt-0.5">{@html icons.check}</span>
								<span>Distinguish between $100 problems and $100,000 problems</span>
							</div>
							<div class="flex items-start gap-2 text-xs text-gray-600">
								<span class="text-primary-600 mt-0.5">{@html icons.check}</span>
								<span>Let users talk 80% of the time in discovery</span>
							</div>
							<div class="flex items-start gap-2 text-xs text-gray-600">
								<span class="text-primary-600 mt-0.5">{@html icons.check}</span>
								<span>Ship and iterate rather than planning endlessly</span>
							</div>
						</div>
						<a href="#" class="text-primary-600 hover:text-primary-700 text-sm font-medium inline-flex items-center gap-1">
							Read more {@html icons.arrowRight}
						</a>
					</div>
				</div>

				<!-- Featured Article 4 -->
				<div class="bg-white border border-gray-200 rounded-2xl overflow-hidden hover:shadow-lg transition-shadow">
					<div class="p-6">
						<div class="text-xs text-primary-600 font-semibold uppercase tracking-wide mb-2">Sep 12, 2025</div>
						<h3 class="font-bold text-xl mb-3 text-gray-900">What is Asymmetry?</h3>
						<p class="text-sm text-gray-600 mb-4 leading-relaxed">
							The founding manifesto: "The biggest shifts in my life came from tiny insights that changed how I played the game—not from working harder."
						</p>
						<div class="bg-gray-50 p-4 rounded-lg mb-4 border-l-4 border-primary-500">
							<p class="text-xs text-gray-700 italic">
								"Competitive advantages come from tiny bets where the downside was basically nothing and the upside made all the difference."
							</p>
						</div>
						<a href="#" class="text-primary-600 hover:text-primary-700 text-sm font-medium inline-flex items-center gap-1">
							Read more {@html icons.arrowRight}
						</a>
					</div>
				</div>
			</div>

			<div class="text-center">
				<p class="text-lg text-gray-600 mb-8 max-w-2xl mx-auto">
					Every week, you'll get actionable insights from builders who've been there. The kind of tactical knowledge that shifts your approach and saves you months of trial and error.
				</p>
				<a href="#subscribe" class="inline-flex items-center gap-2 bg-gray-900 text-white px-6 py-3 rounded-lg font-medium hover:bg-gray-800 transition-colors">
					Subscribe for free
					{@html icons.arrowRight}
				</a>
			</div>
		</section>

		<!-- Founder Section -->
		<section class="max-w-6xl mx-auto px-6 py-20">
			<div class="bg-gray-950 rounded-3xl p-8 md:p-12 text-white">
				<div class="max-w-3xl mx-auto">
					<span class="inline-block bg-primary-500/20 text-primary-300 px-3 py-1 rounded-full text-xs font-semibold uppercase tracking-wide mb-6">
						About the founder
					</span>
					<h2 class="text-3xl md:text-4xl font-bold mb-6 tracking-tight">
						Written by someone who's been in the trenches
					</h2>
					<div class="space-y-4 text-gray-300 leading-relaxed">
						<p>
							<strong class="text-white">Luke Nascimento</strong> built Arctas from scratch, learning product-market fit through direct user observation. His hands-on marketplace experience taught him to prioritize revenue creation over time savings.
						</p>
						<p>
							He's experienced the full cycle: hypothesis testing, customer discovery, rapid iteration, and scaling. Now he shares the tactical insights that actually moved the needle—not the polished success stories, but the messy, unsexy details that made the difference.
						</p>
						<p class="text-sm italic text-gray-400 border-l-4 border-primary-500 pl-4 py-2">
							"The biggest shifts in my life came from tiny insights that changed how I played the game—not from working harder."
						</p>
					</div>
					<div class="mt-8 pt-8 border-t border-gray-800">
						<h3 class="font-bold text-lg mb-4">Key lessons from building Arctas:</h3>
						<div class="grid grid-cols-1 md:grid-cols-2 gap-4">
							<div class="flex items-start gap-3">
								<span class="text-primary-400 mt-1">{@html icons.check}</span>
								<span class="text-sm">Always test hypotheses with real users</span>
							</div>
							<div class="flex items-start gap-3">
								<span class="text-primary-400 mt-1">{@html icons.check}</span>
								<span class="text-sm">Focus on revenue creation, not time savings</span>
							</div>
							<div class="flex items-start gap-3">
								<span class="text-primary-400 mt-1">{@html icons.check}</span>
								<span class="text-sm">Use "5 whys" to get to root problems</span>
							</div>
							<div class="flex items-start gap-3">
								<span class="text-primary-400 mt-1">{@html icons.check}</span>
								<span class="text-sm">Ship and iterate over endless planning</span>
							</div>
						</div>
					</div>
				</div>
			</div>
		</section>

		<!-- Who It's For Section -->
		<section class="max-w-7xl mx-auto px-6 py-20">
			<div class="mb-16 text-center">
				<span class="inline-block bg-gray-100 text-gray-700 px-3 py-1 rounded-full text-xs font-semibold uppercase tracking-wide mb-6">
					Who it's for
				</span>
				<h2 class="text-4xl md:text-5xl font-bold text-gray-900 mb-6 tracking-tight">
					Built for AI engineers who ship
				</h2>
				<p class="text-xl text-gray-600 max-w-2xl mx-auto leading-relaxed">
					If you're building AI products at a startup and need battle-tested frameworks over theoretical fluff, this is for you.
				</p>
			</div>

			<div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6 max-w-5xl mx-auto">
				<!-- Card 1 -->
				<div class="bg-gray-50 p-6 rounded-xl border-2 border-transparent hover:border-primary-500 transition-colors">
					<div class="text-primary-600 mb-3">{@html icons.productivity}</div>
					<h3 class="font-bold text-gray-900 mb-2">Startup AI Engineers</h3>
					<p class="text-sm text-gray-600 leading-relaxed">You're shipping fast, learning faster, and need tactical insights that apply to production—not academic papers.</p>
				</div>
				
				<!-- Card 2 -->
				<div class="bg-gray-50 p-6 rounded-xl border-2 border-transparent hover:border-primary-500 transition-colors">
					<div class="text-primary-600 mb-3">{@html icons.target}</div>
					<h3 class="font-bold text-gray-900 mb-2">Technical Founders</h3>
					<p class="text-sm text-gray-600 leading-relaxed">You're building the product and the company. You need insights that help you move faster and avoid common pitfalls.</p>
				</div>
				
				<!-- Card 3 -->
				<div class="bg-gray-50 p-6 rounded-xl border-2 border-transparent hover:border-primary-500 transition-colors">
					<div class="text-primary-600 mb-3">{@html icons.sparkles}</div>
					<h3 class="font-bold text-gray-900 mb-2">Product Engineers</h3>
					<p class="text-sm text-gray-600 leading-relaxed">You care about user problems, not just technology. You want to understand what actually creates value.</p>
				</div>
				
				<!-- Card 4 -->
				<div class="bg-gray-50 p-6 rounded-xl border-2 border-transparent hover:border-primary-500 transition-colors">
					<div class="text-primary-600 mb-3">{@html icons.layout}</div>
					<h3 class="font-bold text-gray-900 mb-2">Early-Stage Teams</h3>
					<p class="text-sm text-gray-600 leading-relaxed">You're finding product-market fit and need frameworks for customer discovery, hypothesis testing, and rapid iteration.</p>
				</div>
				
				<!-- Card 5 -->
				<div class="bg-gray-50 p-6 rounded-xl border-2 border-transparent hover:border-primary-500 transition-colors">
					<div class="text-primary-600 mb-3">{@html icons.search}</div>
					<h3 class="font-bold text-gray-900 mb-2">Builders, Not Theorists</h3>
					<p class="text-sm text-gray-600 leading-relaxed">You value practical experience over credentials. You want to learn from people who've actually done it.</p>
				</div>
				
				<!-- Card 6 -->
				<div class="bg-gray-50 p-6 rounded-xl border-2 border-transparent hover:border-primary-500 transition-colors">
					<div class="text-primary-600 mb-3">{@html icons.clock}</div>
					<h3 class="font-bold text-gray-900 mb-2">Time-Conscious Learners</h3>
					<p class="text-sm text-gray-600 leading-relaxed">You're drowning in content. You need signal, not noise. Dense insights you can apply immediately.</p>
				</div>
			</div>

			<!-- CTA -->
			<div class="mt-16 text-center bg-primary-50 rounded-2xl p-8 md:p-12 max-w-3xl mx-auto">
				<h3 class="text-2xl md:text-3xl font-bold text-gray-900 mb-4">
					Ready to level up your AI engineering?
				</h3>
				<p class="text-gray-600 mb-6">
					Join 100,000+ builders getting weekly insights. Free, unsubscribe anytime.
				</p>
				<div class="flex flex-col sm:flex-row items-center justify-center gap-4 max-w-md mx-auto">
					<input 
						type="email" 
						placeholder="Your email address" 
						class="w-full px-4 py-3 rounded-lg border border-gray-200 focus:outline-none focus:ring-2 focus:ring-primary-500/20 focus:border-primary-500 transition-all"
					/>
					<button class="w-full sm:w-auto bg-gray-900 text-white px-6 py-3 rounded-lg font-medium hover:bg-gray-800 transition-colors whitespace-nowrap">
						Subscribe free
					</button>
				</div>
			</div>
		</section>

		<!-- Footer -->
		<footer class="max-w-7xl mx-auto px-6 py-12 border-t border-gray-100">
			<div class="grid grid-cols-1 md:grid-cols-3 gap-8 mb-12">
				<div>
					<div class="flex items-center gap-3 mb-4">
						<div class="text-gray-900">
							<svg width="32" height="26" viewBox="0 0 152 125" fill="none" xmlns="http://www.w3.org/2000/svg">
								<path d="M143.58 84.2131H151.874L141.028 72.9422C125.504 56.7801 104.026 47.6357 81.4839 47.6357H78.9319H73.4028H70.6382C48.309 47.6357 26.8304 56.7801 11.0937 72.9422L0.248047 84.2131H8.54176C30.871 84.2131 52.3495 75.0688 68.0863 58.9067L76.1674 50.613C71.4889 79.1093 30.871 124.193 30.871 124.193H76.38H121.889C121.889 124.193 81.6965 79.7473 76.5927 51.2509L84.0358 59.1193C99.5599 75.0688 121.038 84.2131 143.58 84.2131Z" fill="currentColor"/>
								<path d="M69.362 31.0482L75.9544 24.2431L82.5469 31.0482C95.3064 44.4457 113.17 51.8888 131.671 51.8888H138.476L129.545 42.5318C116.785 29.1342 98.9216 21.6912 80.4203 21.6912H78.2937H73.6152H71.4886C52.9872 21.6912 35.3365 29.1342 22.3643 42.5318L13.4326 52.1014H20.2377C38.7391 52.1014 56.6024 44.4457 69.362 31.0482Z" fill="currentColor"/>
								<path d="M70.638 7.65573L75.9544 2.12659L81.2709 7.65573C91.6912 18.5013 106.152 24.6685 121.251 24.6685H126.78L119.55 17.0127C109.129 6.16712 94.6684 0 79.5696 0H77.8684H74.0405H72.3392C57.2404 0 42.7796 6.16712 32.3593 17.0127L25.1289 24.6685H30.658C45.7568 24.6685 60.2177 18.5013 70.638 7.65573Z" fill="currentColor"/>
							</svg>
						</div>
						<span class="font-bold text-lg">Asymmetry</span>
					</div>
					<p class="text-sm text-gray-600 leading-relaxed">
						Actionable AI engineering insights via curated field notes from experienced builders.
					</p>
				</div>
				
				<div>
					<h4 class="font-bold text-sm text-gray-900 mb-4">Newsletter</h4>
					<div class="space-y-3 text-sm text-gray-600">
						<a href="#" class="block hover:text-gray-900">Archive</a>
						<a href="#" class="block hover:text-gray-900">About</a>
						<a href="#" class="block hover:text-gray-900">Subscribe</a>
					</div>
				</div>

				<div>
					<h4 class="font-bold text-sm text-gray-900 mb-4">Connect</h4>
					<div class="space-y-3 text-sm text-gray-600">
						<a href="https://twitter.com/asymmetry" class="block hover:text-gray-900">Twitter</a>
						<a href="#" class="block hover:text-gray-900">Discord</a>
						<a href="mailto:hello@asymmetry.co" class="block hover:text-gray-900">Contact</a>
					</div>
				</div>
			</div>

			<div class="flex flex-col md:flex-row justify-between items-center pt-8 border-t border-gray-100 text-sm text-gray-500">
				<div class="mb-4 md:mb-0">
					<p>© 2025 Asymmetry. All rights reserved.</p>
				</div>
				<div class="flex gap-6">
					<a href="#" class="hover:text-gray-900">Privacy Policy</a>
					<a href="#" class="hover:text-gray-900">Terms of Service</a>
				</div>
			</div>
		</footer>

	</main>
</div>

