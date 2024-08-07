---
layout: single
title: "Term Surrounder"
permalink: /term-surround/
author_profile: true
classes: 
---



Easily surround each line of your search terms with quotes. Perfect for preparing precise search queries. Paste your terms (one per line), click to add quotes, and copy the result. All processing happens in your browser - no data is transferred.

<div id="term-surrounder" style="max-width: 600px; margin: 0 auto;">
	<textarea id="input" style="width: 100%; height: 150px; margin-bottom: 10px;" placeholder="Paste your search terms here, one per line..."></textarea>
	<div style="display: flex; gap: 10px; margin-bottom: 10px;">
		<button onclick="processText()" style="flex: 1;">Surround with Quotes</button>
		<button onclick="copyToClipboard()" style="flex: 1;">Copy to Clipboard</button>
	</div>
	<textarea id="output" style="width: 100%; height: 150px; margin-bottom: 10px;" readonly></textarea>
	<div id="stats" style="font-size: 0.875rem;"></div>
</div>

<script>
function processText() {
	const input = document.getElementById('input').value;
	const lines = input.split('\n');
	const processedLines = lines.map(line => `"${line.trim()}"`);
	const output = processedLines.join('\n');
	
	document.getElementById('output').value = output;
	updateStats(lines.length, processedLines.length);
}

function copyToClipboard() {
	const output = document.getElementById('output');
	output.select();
	document.execCommand('copy');
	
	const button = event.target;
	const originalText = button.textContent;
	button.textContent = 'Copied!';
	button.style.backgroundColor = '#2ecc71';
	
	setTimeout(() => {
		button.textContent = originalText;
		button.style.backgroundColor = '';
	}, 2000);
}

function updateStats(inputLines, outputLines) {
	const stats = document.getElementById('stats');
	stats.innerHTML = `
		<strong>Input terms:</strong> ${inputLines}
		&nbsp;|&nbsp;
		<strong>Output terms:</strong> ${outputLines}
	`;
}
</script>

## Privacy and Security

Term Surrounder operates entirely within your web browser. No data is sent to any external servers, ensuring that your terms remain private and secure on your local machine.

If you'd like to download a copy that you can run locally, you can find this on [Github](https://github.com/jur1st/term_surrounder/tree/main) . 

## How to Use

1. Paste your search terms into the input area, with one term per line.
2. Click the "Surround with Quotes" button to process your terms.
3. The processed terms will appear in the output area below.
4. Click "Copy to Clipboard" to copy the processed terms.