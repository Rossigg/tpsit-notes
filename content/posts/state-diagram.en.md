--- 
title: "State Diagram"
description: "Describe the behavior of systems" # update text !
date: 2021-02-16T12:01:15+01:00 # update date !

draft: true # toggle to false when final version is approved !

languageName: "English"
author: ["Giacomo", "Nicolò", "Lorenzo", "Stefano"] 

tags: ["Software Requirements"]      
categories: ["Software Requirements"]   
---  

<!-- Write content Down Here :) -->
<style>
		/* webkit printing magic: print all background colors */
		html {
			-webkit-print-color-adjust: exact;
		}

		* {
			box-sizing: border-box;
			-webkit-print-color-adjust: exact;
		}

		html,
		body {
			margin: 0;
			padding: 0;
		}

		@media only screen {
			body {
				margin: 2em auto;
				max-width: 900px;
				color: rgb(55, 53, 47);
			}
		}

		body {
			line-height: 1.5;
			white-space: pre-wrap;
		}

		a,
		a.visited {
			color: inherit;
			text-decoration: underline;
		}

		.pdf-relative-link-path {
			font-size: 80%;
			color: #444;
		}

		h1,
		h2,
		h3 {
			letter-spacing: -0.01em;
			line-height: 1.2;
			font-weight: 600;
			margin-bottom: 0;
		}

		.page-title {
			font-size: 2.5rem;
			font-weight: 700;
			margin-top: 0;
			margin-bottom: 0.75em;
		}

		h1 {
			font-size: 1.875rem;
			margin-top: 1.875rem;
		}

		h2 {
			font-size: 1.5rem;
			margin-top: 1.5rem;
		}

		h3 {
			font-size: 1.25rem;
			margin-top: 1.25rem;
		}

		.source {
			border: 1px solid #ddd;
			border-radius: 3px;
			padding: 1.5em;
			word-break: break-all;
		}

		.callout {
			border-radius: 3px;
			padding: 1rem;
		}

		figure {
			margin: 1.25em 0;
			page-break-inside: avoid;
		}

		figcaption {
			opacity: 0.5;
			font-size: 85%;
			margin-top: 0.5em;
		}

		mark {
			background-color: transparent;
		}

		.indented {
			padding-left: 1.5em;
		}

		hr {
			background: transparent;
			display: block;
			width: 100%;
			height: 1px;
			visibility: visible;
			border: none;
			border-bottom: 1px solid rgba(55, 53, 47, 0.09);
		}

		img {
			max-width: 100%;
		}

		@media only print {
			img {
				max-height: 100vh;
				object-fit: contain;
			}
		}

		@page {
			margin: 1in;
		}

		.collection-content {
			font-size: 0.875rem;
		}

		.column-list {
			display: flex;
			justify-content: space-between;
		}

		.column {
			padding: 0 1em;
		}

		.column:first-child {
			padding-left: 0;
		}

		.column:last-child {
			padding-right: 0;
		}

		.table_of_contents-item {
			display: block;
			font-size: 0.875rem;
			line-height: 1.3;
			padding: 0.125rem;
		}

		.table_of_contents-indent-1 {
			margin-left: 1.5rem;
		}

		.table_of_contents-indent-2 {
			margin-left: 3rem;
		}

		.table_of_contents-indent-3 {
			margin-left: 4.5rem;
		}

		.table_of_contents-link {
			text-decoration: none;
			opacity: 0.7;
			border-bottom: 1px solid rgba(55, 53, 47, 0.18);
		}

		table,
		th,
		td {
			border: 1px solid rgba(55, 53, 47, 0.09);
			border-collapse: collapse;
		}

		table {
			border-left: none;
			border-right: none;
		}

		th,
		td {
			font-weight: normal;
			padding: 0.25em 0.5em;
			line-height: 1.5;
			min-height: 1.5em;
			text-align: left;
		}

		th {
			color: rgba(55, 53, 47, 0.6);
		}

		ol,
		ul {
			margin: 0;
			margin-block-start: 0.6em;
			margin-block-end: 0.6em;
		}

		li>ol:first-child,
		li>ul:first-child {
			margin-block-start: 0.6em;
		}

		ul>li {
			list-style: disc;
		}

		ul.to-do-list {
			text-indent: -1.7em;
		}

		ul.to-do-list>li {
			list-style: none;
		}

		.to-do-children-checked {
			text-decoration: line-through;
			opacity: 0.375;
		}

		ul.toggle>li {
			list-style: none;
		}

		ul {
			padding-inline-start: 1.7em;
		}

		ul>li {
			padding-left: 0.1em;
		}

		ol {
			padding-inline-start: 1.6em;
		}

		ol>li {
			padding-left: 0.2em;
		}

		.mono ol {
			padding-inline-start: 2em;
		}

		.mono ol>li {
			text-indent: -0.4em;
		}

		.toggle {
			padding-inline-start: 0em;
			list-style-type: none;
		}

		/* Indent toggle children */
		.toggle>li>details {
			padding-left: 1.7em;
		}

		.toggle>li>details>summary {
			margin-left: -1.1em;
		}

		.selected-value {
			display: inline-block;
			padding: 0 0.5em;
			background: rgba(206, 205, 202, 0.5);
			border-radius: 3px;
			margin-right: 0.5em;
			margin-top: 0.3em;
			margin-bottom: 0.3em;
			white-space: nowrap;
		}

		.collection-title {
			display: inline-block;
			margin-right: 1em;
		}

		time {
			opacity: 0.5;
		}

		.icon {
			display: inline-block;
			max-width: 1.2em;
			max-height: 1.2em;
			text-decoration: none;
			vertical-align: text-bottom;
			margin-right: 0.5em;
		}

		img.icon {
			border-radius: 3px;
		}

		.user-icon {
			width: 1.5em;
			height: 1.5em;
			border-radius: 100%;
			margin-right: 0.5rem;
		}

		.user-icon-inner {
			font-size: 0.8em;
		}

		.text-icon {
			border: 1px solid #000;
			text-align: center;
		}

		.page-cover-image {
			display: block;
			object-fit: cover;
			width: 100%;
			height: 30vh;
		}

		.page-header-icon {
			font-size: 3rem;
			margin-bottom: 1rem;
		}

		.page-header-icon-with-cover {
			margin-top: -0.72em;
			margin-left: 0.07em;
		}

		.page-header-icon img {
			border-radius: 3px;
		}

		.link-to-page {
			margin: 1em 0;
			padding: 0;
			border: none;
			font-weight: 500;
		}

		p>.user {
			opacity: 0.5;
		}

		td>.user,
		td>time {
			white-space: nowrap;
		}

		input[type="checkbox"] {
			transform: scale(1.5);
			margin-right: 0.6em;
			vertical-align: middle;
		}

		p {
			margin-top: 0.5em;
			margin-bottom: 0.5em;
		}

		.image {
			border: none;
			margin: 1.5em 0;
			padding: 0;
			border-radius: 0;
			text-align: center;
		}

		.code,
		code {
			background: rgba(135, 131, 120, 0.15);
			border-radius: 3px;
			padding: 0.2em 0.4em;
			border-radius: 3px;
			font-size: 85%;
			tab-size: 2;
		}

		code {
			color: #eb5757;
		}

		.code {
			padding: 1.5em 1em;
		}

		.code-wrap {
			white-space: pre-wrap;
			word-break: break-all;
		}

		.code>code {
			background: none;
			padding: 0;
			font-size: 100%;
			color: inherit;
		}

		blockquote {
			font-size: 1.25em;
			margin: 1em 0;
			padding-left: 1em;
			border-left: 3px solid rgb(55, 53, 47);
		}

		.bookmark {
			text-decoration: none;
			max-height: 8em;
			padding: 0;
			display: flex;
			width: 100%;
			align-items: stretch;
		}

		.bookmark-title {
			font-size: 0.85em;
			overflow: hidden;
			text-overflow: ellipsis;
			height: 1.75em;
			white-space: nowrap;
		}

		.bookmark-text {
			display: flex;
			flex-direction: column;
		}

		.bookmark-info {
			flex: 4 1 180px;
			padding: 12px 14px 14px;
			display: flex;
			flex-direction: column;
			justify-content: space-between;
		}

		.bookmark-image {
			width: 33%;
			flex: 1 1 180px;
			display: block;
			position: relative;
			object-fit: cover;
			border-radius: 1px;
		}

		.bookmark-description {
			color: rgba(55, 53, 47, 0.6);
			font-size: 0.75em;
			overflow: hidden;
			max-height: 4.5em;
			word-break: break-word;
		}

		.bookmark-href {
			font-size: 0.75em;
			margin-top: 0.25em;
		}

		.sans {
			font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Helvetica, "Apple Color Emoji", Arial, sans-serif, "Segoe UI Emoji", "Segoe UI Symbol";
		}

		.code {
			font-family: "SFMono-Regular", Consolas, "Liberation Mono", Menlo, Courier, monospace;
		}

		.serif {
			font-family: Lyon-Text, Georgia, YuMincho, "Yu Mincho", "Hiragino Mincho ProN", "Hiragino Mincho Pro", "Songti TC", "Songti SC", "SimSun", "Nanum Myeongjo", NanumMyeongjo, Batang, serif;
		}

		.mono {
			font-family: iawriter-mono, Nitti, Menlo, Courier, monospace;
		}

		.pdf .sans {
			font-family: Inter, -apple-system, BlinkMacSystemFont, "Segoe UI", Helvetica, "Apple Color Emoji", Arial, sans-serif, "Segoe UI Emoji", "Segoe UI Symbol", 'Twemoji', 'Noto Color Emoji', 'Noto Sans CJK SC', 'Noto Sans CJK KR';
		}

		.pdf .code {
			font-family: Source Code Pro, "SFMono-Regular", Consolas, "Liberation Mono", Menlo, Courier, monospace, 'Twemoji', 'Noto Color Emoji', 'Noto Sans Mono CJK SC', 'Noto Sans Mono CJK KR';
		}

		.pdf .serif {
			font-family: PT Serif, Lyon-Text, Georgia, YuMincho, "Yu Mincho", "Hiragino Mincho ProN", "Hiragino Mincho Pro", "Songti TC", "Songti SC", "SimSun", "Nanum Myeongjo", NanumMyeongjo, Batang, serif, 'Twemoji', 'Noto Color Emoji', 'Noto Sans CJK SC', 'Noto Sans CJK KR';
		}

		.pdf .mono {
			font-family: PT Mono, iawriter-mono, Nitti, Menlo, Courier, monospace, 'Twemoji', 'Noto Color Emoji', 'Noto Sans Mono CJK SC', 'Noto Sans Mono CJK KR';
		}

		.highlight-default {}

		.highlight-gray {
			color: rgb(155, 154, 151);
		}

		.highlight-brown {
			color: rgb(100, 71, 58);
		}

		.highlight-orange {
			color: rgb(217, 115, 13);
		}

		.highlight-yellow {
			color: rgb(223, 171, 1);
		}

		.highlight-teal {
			color: rgb(15, 123, 108);
		}

		.highlight-blue {
			color: rgb(11, 110, 153);
		}

		.highlight-purple {
			color: rgb(105, 64, 165);
		}

		.highlight-pink {
			color: rgb(173, 26, 114);
		}

		.highlight-red {
			color: rgb(224, 62, 62);
		}

		.highlight-gray_background {
			background: rgb(235, 236, 237);
		}

		.highlight-brown_background {
			background: rgb(233, 229, 227);
		}

		.highlight-orange_background {
			background: rgb(250, 235, 221);
		}

		.highlight-yellow_background {
			background: rgb(251, 243, 219);
		}

		.highlight-teal_background {
			background: rgb(221, 237, 234);
		}

		.highlight-blue_background {
			background: rgb(221, 235, 241);
		}

		.highlight-purple_background {
			background: rgb(234, 228, 242);
		}

		.highlight-pink_background {
			background: rgb(244, 223, 235);
		}

		.highlight-red_background {
			background: rgb(251, 228, 228);
		}

		.block-color-default {
			color: inherit;
			fill: inherit;
		}

		.block-color-gray {
			color: rgba(55, 53, 47, 0.6);
			fill: rgba(55, 53, 47, 0.6);
		}

		.block-color-brown {
			color: rgb(100, 71, 58);
			fill: rgb(100, 71, 58);
		}

		.block-color-orange {
			color: rgb(217, 115, 13);
			fill: rgb(217, 115, 13);
		}

		.block-color-yellow {
			color: rgb(223, 171, 1);
			fill: rgb(223, 171, 1);
		}

		.block-color-teal {
			color: rgb(15, 123, 108);
			fill: rgb(15, 123, 108);
		}

		.block-color-blue {
			color: rgb(11, 110, 153);
			fill: rgb(11, 110, 153);
		}

		.block-color-purple {
			color: rgb(105, 64, 165);
			fill: rgb(105, 64, 165);
		}

		.block-color-pink {
			color: rgb(173, 26, 114);
			fill: rgb(173, 26, 114);
		}

		.block-color-red {
			color: rgb(224, 62, 62);
			fill: rgb(224, 62, 62);
		}

		.block-color-gray_background {
			background: rgb(235, 236, 237);
		}

		.block-color-brown_background {
			background: rgb(233, 229, 227);
		}

		.block-color-orange_background {
			background: rgb(250, 235, 221);
		}

		.block-color-yellow_background {
			background: rgb(251, 243, 219);
		}

		.block-color-teal_background {
			background: rgb(221, 237, 234);
		}

		.block-color-blue_background {
			background: rgb(221, 235, 241);
		}

		.block-color-purple_background {
			background: rgb(234, 228, 242);
		}

		.block-color-pink_background {
			background: rgb(244, 223, 235);
		}

		.block-color-red_background {
			background: rgb(251, 228, 228);
		}

		.select-value-color-default {
			background-color: rgba(206, 205, 202, 0.5);
		}

		.select-value-color-gray {
			background-color: rgba(155, 154, 151, 0.4);
		}

		.select-value-color-brown {
			background-color: rgba(140, 46, 0, 0.2);
		}

		.select-value-color-orange {
			background-color: rgba(245, 93, 0, 0.2);
		}

		.select-value-color-yellow {
			background-color: rgba(233, 168, 0, 0.2);
		}

		.select-value-color-green {
			background-color: rgba(0, 135, 107, 0.2);
		}

		.select-value-color-blue {
			background-color: rgba(0, 120, 223, 0.2);
		}

		.select-value-color-purple {
			background-color: rgba(103, 36, 222, 0.2);
		}

		.select-value-color-pink {
			background-color: rgba(221, 0, 129, 0.2);
		}

		.select-value-color-red {
			background-color: rgba(255, 0, 26, 0.2);
		}

		.checkbox {
			display: inline-flex;
			vertical-align: text-bottom;
			width: 16;
			height: 16;
			background-size: 16px;
			margin-left: 2px;
			margin-right: 5px;
		}

		.checkbox-on {
			background-image: url("data:image/svg+xml;charset=UTF-8,%3Csvg%20width%3D%2216%22%20height%3D%2216%22%20viewBox%3D%220%200%2016%2016%22%20fill%3D%22none%22%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%3E%0A%3Crect%20width%3D%2216%22%20height%3D%2216%22%20fill%3D%22%2358A9D7%22%2F%3E%0A%3Cpath%20d%3D%22M6.71429%2012.2852L14%204.9995L12.7143%203.71436L6.71429%209.71378L3.28571%206.2831L2%207.57092L6.71429%2012.2852Z%22%20fill%3D%22white%22%2F%3E%0A%3C%2Fsvg%3E");
		}

		.checkbox-off {
			background-image: url("data:image/svg+xml;charset=UTF-8,%3Csvg%20width%3D%2216%22%20height%3D%2216%22%20viewBox%3D%220%200%2016%2016%22%20fill%3D%22none%22%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%3E%0A%3Crect%20x%3D%220.75%22%20y%3D%220.75%22%20width%3D%2214.5%22%20height%3D%2214.5%22%20fill%3D%22white%22%20stroke%3D%22%2336352F%22%20stroke-width%3D%221.5%22%2F%3E%0A%3C%2Fsvg%3E");
		}
	</style>

<!-- placeholder text || you can use Markdown or HTML to add some content -->
<article id="ddb2e2bc-1b52-48be-ae07-4ffc93c92b99" class="page sans">
		<header>
			<h1 class="page-title">State Diagram</h1>
		</header>
		<div class="page-body">
			<p id="dc1e3932-bbb7-4460-a0af-170ad378767d" class="">A <strong>state diagram</strong> consists of
				<em>states</em>, <em>transitions</em>, <em>events</em>, and <em>activities</em>. You use state diagrams
				to illustrate the <strong>dynamic view</strong> of a system. They are especially important in modeling
				the behavior of an <em>interface</em>, <em>class</em>, or <em>collaboration</em>. State diagrams
				emphasize the <strong>event-ordered</strong> behavior of an object, which is especially useful in
				modeling reactive systems.
			</p>
			<h1 id="f90bc416-1b70-46d5-a39e-c29bddc9d005" class="">Basic State Chart Diagram Symbols and Notations</h1>
			<h2 id="b77f1e68-dca2-4ab2-b5c8-f7e627532a77" class="">State</h2>
			<p id="92ea89aa-2ed3-4451-a74d-1d7e378ed0cd" class="">A <strong>state </strong>is a condition during the
				life of an object during which it <em>satisfies some condition</em>, <em>performs some activity</em>, or
				<em>waits for some external event</em>.
			</p>
			<div id="0a1df0f8-694c-422c-b2be-b29b2d10c406" class="column-list">
				<div id="223fa283-31d9-48d9-9dbe-1c949a9b59d3" style="width:56.25%" class="column">
					<figure id="c839f8fd-7e2b-4f01-a70b-7d796fd60a34" class="image"><a
							href="State%20Diagram%20c839f8fd7e2b4f01a70b7d796fd60a34/State_simple.svg"><img
								style="width:240px"
								src="State%20Diagram%20c839f8fd7e2b4f01a70b7d796fd60a34/State_simple.svg" /></a>
						<figcaption>State is represented by a rectangle</figcaption>
					</figure>
				</div>
				<div id="b98373db-0bce-40b1-85af-f423770e271f" style="width:43.74999999999999%" class="column">
					<figure id="4d0a0c22-b2d0-41c5-b3e6-88d6178b471f" class="image"><a
							href="State%20Diagram%20c839f8fd7e2b4f01a70b7d796fd60a34/State_complex.svg"><img
								style="width:288px"
								src="State%20Diagram%20c839f8fd7e2b4f01a70b7d796fd60a34/State_complex.svg" /></a>
						<figcaption>A state with internal activities</figcaption>
					</figure>
					<p id="3f05d8a1-75c7-4871-a747-194e199bcd3a" class="">
					</p>
				</div>
			</div>
			<h3 id="43eb9697-1454-4f99-9d3b-906a6d4a3c45" class="">Initial and Final States</h3>
			<ul id="f21befa6-caff-4b21-a44f-4dc21078a9c5" class="bulleted-list">
				<li>The <strong>initial state</strong> of a state machine diagram, known as an <em>initial
						pseudo-state</em>. A <em>transition </em>from this state will show the <strong>first real
						state.</strong></li>
			</ul>
			<figure id="961eee3f-0be6-41e5-b38c-3512a094833e" class="image"><a
					href="State%20Diagram%20c839f8fd7e2b4f01a70b7d796fd60a34/InitialState.svg"><img style="width:192px"
						src="State%20Diagram%20c839f8fd7e2b4f01a70b7d796fd60a34/InitialState.svg" /></a>
				<figcaption>A filled circle followed by an arrow represents the object&#x27;s initial state</figcaption>
			</figure>
			<ul id="00e00f86-7fb5-43c2-b979-ed6214b6bbc0" class="bulleted-list">
				<li>The <strong>final state</strong> of a state machine diagram. An <em>open loop</em> state machine
					represents an object that may <em>terminate before the system terminates</em>, while a <em>closed
						loop</em> state machine diagram does <em>not have a final state</em>; if it is the case, then
					the object lives until the entire system terminates.</li>
			</ul>
			<figure id="2269fe70-ce42-429d-b402-7626fbc54073" class="image"><a
					href="State%20Diagram%20c839f8fd7e2b4f01a70b7d796fd60a34/FinalState.svg"><img style="width:192px"
						src="State%20Diagram%20c839f8fd7e2b4f01a70b7d796fd60a34/FinalState.svg" /></a>
				<figcaption>An arrow pointing to a filled circle nested inside another circle represents the
					object&#x27;s final state</figcaption>
			</figure>
			<p id="2839c1cd-9e2a-4999-aee5-a75b6e1050df" class="">
			</p>
			<h2 id="efaa8120-1b3a-482c-a3b3-75c9789f0ab4" class="">Event</h2>
			<p id="9d351384-23ed-496b-b95b-e8587dcbd32a" class="">An <strong>event</strong> is the <em>specification
				</em>of a <em>significant occurrence</em>. For a state machine, an event is the occurrence of a stimulus
				that can trigger a state transition.</p>
			<h2 id="d30ceda6-e151-42eb-9478-29fd1f1420f3" class="">Action</h2>
			<p id="0b17b57f-a6d3-4708-9a56-642fd9e3b017" class="">An <strong>action</strong> is an <em>executable
					computation</em>. Actions may include <em>operations</em>, the <em>creation </em>or
				<em>destruction</em> of other objects, or the <em>sending </em>of signals to other objects.
			</p>
			<h2 id="a779ee98-6013-45ab-ac01-0965e771e1a0" class="">Transition</h2>
			<p id="5752c3a7-87cb-43fc-8dd1-8442a4995429" class="">A <strong>transition </strong>is a
				<em>relationship</em> between <em>two states</em> indicating that an object in the <em>first state</em>
				will, when a specified set of events and conditions are <em>satisfied</em>, perform certain <em>action/s
				</em>and enter the <em>second state</em>.
			</p>
			<div id="ec98d756-a9e8-442d-9c6e-d9816fdca231" class="column-list">
				<div id="e69502da-af32-4092-80e3-79f089384777" style="width:50%" class="column">
					<p id="16a244e0-bfa3-496c-a3c7-ad916c996459" class="">A transition has:</p>
				</div>
				<div id="4e5ef2b5-aec6-451b-bb73-7821bafb3367" style="width:50%" class="column">
					<ol id="1807bb72-a093-49c5-b57d-581e6429076b" class="numbered-list" start="1">
						<li>source state</li>
					</ol>
					<ol id="f7aed410-62c7-47a9-b996-707629754371" class="numbered-list" start="2">
						<li>event trigger</li>
					</ol>
					<ol id="83c5a3a9-8636-4d9c-b2a7-e5d1643f4b18" class="numbered-list" start="3">
						<li>action/s</li>
					</ol>
					<ol id="24325d1c-11e9-4329-a7a6-53bf1849f382" class="numbered-list" start="4">
						<li>target state</li>
					</ol>
				</div>
			</div>
			<figure id="e4101442-9725-4af1-9e65-35744c3bfcee" class="image"><a
					href="State%20Diagram%20c839f8fd7e2b4f01a70b7d796fd60a34/Arrow.svg"><img style="width:240px"
						src="State%20Diagram%20c839f8fd7e2b4f01a70b7d796fd60a34/Arrow.svg" /></a>
				<figcaption>A solid arrow represents the path between different states of an object</figcaption>
			</figure>
			<figure class="block-color-gray_background callout" style="white-space:pre-wrap;display:flex"
				id="c4c37971-96ff-4433-b6d0-8e5cfd668386">
				<div style="font-size:1.5em"><span class="icon">❕</span></div>
				<div style="width:100%">A <strong>self-transition</strong> is a transition whose <em>source</em> and
					<em>target states</em> are <em>the same</em>
				</div>
			</figure>
			<h1 id="4e105d4c-3f8b-4613-98ad-5f9c9e27c734" class="">Advanced State Chart Diagram Concepts</h1>
			<h2 id="67a431a5-6343-4595-a104-db66c22d41fd" class="">Constraints</h2>
			<p id="0d250820-81a8-422f-943c-29ac0558463f" class="">It is possible to add <strong>constraints </strong>to
				transitions, the semantics is that a transition is <em>enabled </em>when the constraint is <em>true</em>
			</p>
			<figure id="85249414-d460-40a6-ba4d-cd843e9ce7ff" class="image"><a
					href="State%20Diagram%20c839f8fd7e2b4f01a70b7d796fd60a34/Contraint.svg"><img style="width:463px"
						src="State%20Diagram%20c839f8fd7e2b4f01a70b7d796fd60a34/Contraint.svg" /></a>
				<figcaption>Constraint ”[not last copy]” and ”[last copy]” are used to distinguish the two transitions
					with the event ”copyBorrowed()”</figcaption>
			</figure>
			<h2 id="ec892bc8-ba47-4c4d-8cbb-40724554dd48" class="">Substates</h2>
			<p id="bfb1a42b-9982-459f-a6a6-79e4fcb60318" class="">A <strong>sub-state</strong> is one which has <em>no
					substructure</em>. A state which has <em>sub-states </em>(nested states) is called a
				<strong>composite state</strong>. Sub-states may be nested to any level. A nested state machine may have
				at most one initial state and one final state. Sub-states are used to simplify complex flat state
				machines by showing that some states are only possible within a particular context.
			</p>
			<figure id="a38c2206-6f0e-44a4-8912-13ba9955128e" class="image"><a
					href="State%20Diagram%20c839f8fd7e2b4f01a70b7d796fd60a34/Substates.svg"><img style="width:432px"
						src="State%20Diagram%20c839f8fd7e2b4f01a70b7d796fd60a34/Substates.svg" /></a>
				<figcaption>The <em>Cooling </em>composite state has 3 nested state (sub-state) that run in sequence
				</figcaption>
			</figure>
			<h2 id="caa5f091-301e-4baa-a2b4-8f519b63828a" class="">History States</h2>
			<p id="9f3dc02d-7739-4adf-b096-43e0394022ad" class="">When a transition enters a <em>composite state</em>,
				the action of the nested state machine starts <em>over again</em> at the <em>initial state</em>.
				<strong>History states</strong> allow the state machine to <strong>re-enter the last sub-state</strong>
				that was active in it prior to leaving the composite state.
			</p>
			<figure id="d36a225e-95f7-48af-bf35-5f815f1f784b" class="image"><a
					href="State%20Diagram%20c839f8fd7e2b4f01a70b7d796fd60a34/HistoryState.svg"><img style="width:288px"
						src="State%20Diagram%20c839f8fd7e2b4f01a70b7d796fd60a34/HistoryState.svg" /></a>
				<figcaption>The Shallow History State is represented by an H in a circle</figcaption>
			</figure>
			<h2 id="840412d5-d49d-4610-9b9e-dfc40cb0b382" class="">Concurrent State</h2>
			<p id="0239cc55-7998-4c83-98af-fbd6974b6327" class=""><strong>Concurrent Sub-states</strong> are
				<em>independent </em>and can complete at different times and each sub-state is separated from the others
				by a dashed line.
			</p>
			<figure id="d0d5fc62-fe3f-4eee-816f-ca2a387eb0b3" class="image"><a
					href="State%20Diagram%20c839f8fd7e2b4f01a70b7d796fd60a34/ConcurrentState.svg"><img
						style="width:355px"
						src="State%20Diagram%20c839f8fd7e2b4f01a70b7d796fd60a34/ConcurrentState.svg" /></a>
				<figcaption>Into the <em>On </em>state 4 nested state run into 2 different parallelism. The 2 sub-states
					are divided by a dashed line</figcaption>
			</figure>
			<h1 id="1803584e-b3ff-41dd-88b8-fb04846d1687" class="">Example</h1>
			<p id="db2751f7-0d23-43d3-889f-78c014e42860" class="">Here is an example of the process life in a CPU.</p>
			<p id="46d9ac63-1655-4a82-bad7-35b2a76f036a" class="">When a <strong>new process</strong> is <em>ready for
					the execution</em>, it will <strong>moved to the ready queue</strong> where it wait for the CPU
				assignment. When the <em>CPU is free</em> for this process, it will <strong>moved to the running
					queue</strong>. In the running state 2 cases can occur: the <em>process finished or terminated</em>
				his life, so it will <strong>moved out of the running state</strong>; or the <em>resource is
					unavailable</em>, so it will <strong>moved to the blocked queue</strong> and when the <em>resource
					is freed</em>, it will <strong>moved again to the ready queue</strong>.</p>
			<p id="0496adc0-eb28-42dc-bfde-05d584c7edf1" class="">
			</p>
			<figure id="a452d564-0687-42e5-b99b-82706335d037" class="image"><a
					href="State%20Diagram%20c839f8fd7e2b4f01a70b7d796fd60a34/CPUStateDiagram.svg"><img
						style="width:471px"
						src="State%20Diagram%20c839f8fd7e2b4f01a70b7d796fd60a34/CPUStateDiagram.svg" /></a>
				<figcaption>State Diagram - CPU Execution</figcaption>
			</figure>
			<p id="817c1eb4-da9f-4381-b8b0-59e09fc19c9a" class="">
			</p>
		</div>
	</article>