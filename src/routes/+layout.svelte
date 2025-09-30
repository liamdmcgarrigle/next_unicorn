<script lang="ts">
	import Header from './Header.svelte';
	import '../app.css';
	let { children } = $props();

	// Random startup buzzwords for the footer
	const buzzwords = [
		'Disrupting disruption since 2024',
		'Pre-revenue but post-hype',
		'Blockchain-ready (we think)',
		'AI-powered (ChatGPT wrapper)',
		'Web3-curious, Web2-realistic',
		'Metaverse-optional',
		'Carbon-neutral promises',
		'GDPR-compliant (probably)'
	];
	
	const randomBuzzword = buzzwords[Math.floor(Math.random() * buzzwords.length)];
</script>

<div class="app">
	<Header />
	
	<div class="growth-ticker">
		<span>📈 Current valuation: ${Math.floor(Math.random() * 900 + 100)}M</span>
		<span>•</span>
		<span>🚀 Runway: {Math.floor(Math.random() * 12 + 1)} months</span>
		<span>•</span>
		<span>🔥 Burn rate: Yes</span>
	</div>
	
	<main>
		{@render children()}
	</main>
	
	<footer>
		<div class="footer-content">
			<p class="buzzword">{randomBuzzword}</p>
			
			<div class="footer-links">
				<a href="https://github.com/yourusername/next_unicorn">GitHub</a>
				<span class="separator">•</span>
				<a href="/pitch">Pitch Deck</a>
				<span class="separator">•</span>
				<a href="mailto:investors@nextunicorn.ai">investors@nextunicorn.ai</a>
			</div>
			
			<p class="disclaimer">
				Built with <a href="https://svelte.dev">Svelte</a> because React is too mainstream
				<br>
				<span class="copyright">© 2024 Next Unicorn - A subsidiary of hopes and dreams</span>
			</p>
		</div>
		
		<div class="exit-strategy">
			<button onclick={() => alert('Exit strategy: Acquisition by FAANG or bust!')}>
				🎯 View Exit Strategy
			</button>
		</div>
	</footer>
</div>

<style>
	.app {
		display: flex;
		flex-direction: column;
		min-height: 100vh;
		background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
		position: relative;
	}

	.growth-ticker {
		background: rgba(0, 0, 0, 0.9);
		color: #00ff00;
		padding: 0.5rem;
		display: flex;
		justify-content: center;
		align-items: center;
		gap: 1rem;
		font-family: 'Courier New', monospace;
		font-size: 0.85rem;
		overflow: hidden;
		position: sticky;
		top: 0;
		z-index: 10;
		animation: ticker-glow 2s ease-in-out infinite;
	}

	@keyframes ticker-glow {
		0%, 100% { box-shadow: 0 0 10px rgba(0, 255, 0, 0.2); }
		50% { box-shadow: 0 0 20px rgba(0, 255, 0, 0.4); }
	}

	.growth-ticker span {
		white-space: nowrap;
	}

	main {
		flex: 1;
		display: flex;
		flex-direction: column;
		padding: 2rem 1rem;
		width: 100%;
		max-width: 64rem;
		margin: 0 auto;
		box-sizing: border-box;
		background: white;
		border-radius: 16px;
		box-shadow: 0 10px 40px rgba(0, 0, 0, 0.08);
		margin-top: 2rem;
		margin-bottom: 2rem;
	}

	footer {
		background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
		color: white;
		padding: 3rem 1rem 2rem;
		position: relative;
		overflow: hidden;
	}

	footer::before {
		content: '🦄';
		position: absolute;
		font-size: 200px;
		opacity: 0.05;
		right: -50px;
		bottom: -50px;
		transform: rotate(-15deg);
	}

	.footer-content {
		max-width: 64rem;
		margin: 0 auto;
		text-align: center;
		position: relative;
		z-index: 1;
	}

	.buzzword {
		font-size: 1.2rem;
		font-weight: 600;
		margin-bottom: 1.5rem;
		text-transform: uppercase;
		letter-spacing: 0.1em;
		opacity: 0.9;
	}

	.footer-links {
		display: flex;
		justify-content: center;
		align-items: center;
		gap: 1rem;
		margin-bottom: 2rem;
		flex-wrap: wrap;
	}

	.footer-links a {
		color: white;
		text-decoration: none;
		font-weight: 600;
		transition: all 0.2s;
		padding: 0.5rem 1rem;
		border-radius: 20px;
		background: rgba(255, 255, 255, 0.1);
		backdrop-filter: blur(10px);
	}

	.footer-links a:hover {
		background: rgba(255, 255, 255, 0.2);
		transform: translateY(-2px);
	}

	.separator {
		opacity: 0.5;
	}

	.disclaimer {
		font-size: 0.85rem;
		opacity: 0.8;
		line-height: 1.6;
	}

	.disclaimer a {
		color: white;
		font-weight: 600;
		text-decoration: underline;
	}

	.copyright {
		display: block;
		margin-top: 0.5rem;
		font-size: 0.75rem;
		opacity: 0.6;
	}

	.exit-strategy {
		margin-top: 2rem;
		text-align: center;
	}

	.exit-strategy button {
		background: white;
		color: #667eea;
		border: none;
		padding: 0.75rem 2rem;
		border-radius: 30px;
		font-weight: 700;
		font-size: 0.9rem;
		cursor: pointer;
		transition: all 0.3s;
		box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
	}

	.exit-strategy button:hover {
		transform: translateY(-2px) scale(1.05);
		box-shadow: 0 6px 20px rgba(0, 0, 0, 0.3);
	}

	/* Mobile optimizations */
	@media (min-width: 480px) {
		.growth-ticker {
			font-size: 0.9rem;
		}
	}

	@media (max-width: 480px) {
		.footer-links {
			flex-direction: column;
		}
		
		.separator {
			display: none;
		}

		.growth-ticker {
			font-size: 0.7rem;
			gap: 0.5rem;
		}
	}
</style>
