<div class="flex">
	<!-- 1 -->
	<section class="card card--heart" value="1">
		<div class="card__inner card__inner--center">
			<div class="card__symbol card__symbol--big" />
		</div>
	</section>
	<!-- 2 -->
	<section class="card card--heart" value="2">
		<div class="card__inner">
			<div class="card__column">
				<div class="card__symbol" />
				<div class="card__symbol y-rotate" />
			</div>
		</div>
	</section>
	<!-- 3 -->
	<section class="card card--heart" value="3">
		<div class="card__inner">
			<div class="card__column">
				<div class="card__symbol" />
				<div class="card__symbol y-rotate" />
				<div class="card__symbol y-rotate" />
			</div>
		</div>
	</section>
	<!-- 4 -->
	<section class="card card--heart" value="4">
		<div class="card__inner">
			<div class="card__column">
				<div class="card__symbol" />
				<div class="card__symbol xy-rotate" />
			</div>
			<div class="card__column">
				<div class="card__symbol x-rotate" />
				<div class="card__symbol y-rotate" />
			</div>
		</div>
	</section>

	<!-- 5 -->
	<section class="card card--heart" value="5">
		<div class="card__inner">
			<div class="card__column">
				<div class="card__symbol " />
				<div class="card__symbol xy-rotate" />
			</div>
			<div class="card__column card__column--centered">
				<div class="card__symbol" />
			</div>
			<div class="card__column">
				<div class="card__symbol x-rotate" />
				<div class="card__symbol y-rotate" />
			</div>
		</div>
	</section>

	<!-- 6 -->
	<section class="card card--heart" value="6">
		<div class="card__inner">
			<div class="card__column">
				<div class="card__symbol" />
				<div class="card__symbol" />
				<div class="card__symbol y-rotate" />
			</div>
			<div class="card__column">
				<div class="card__symbol" />
				<div class="card__symbol" />
				<div class="card__symbol y-rotate" />
			</div>
		</div>
	</section>

	<!-- 7 -->
	<section class="card card--heart" value="7">
		<div class="card__inner-row">
			<div class="card__row">
				<div class="card__symbol" />
				<div class="card__symbol x-rotate" />
			</div>
			<div class="card__row">
				<div class="card__symbol" />
				<div class="card__symbol x-rotate" />
				<div class="card__symbol x-rotate" />
			</div>
			<div class="card__row">
				<div class="card__symbol xy-rotate" />
				<div class="card__symbol y-rotate" />
			</div>
		</div>
	</section>
</div>

<style>
	.card__row {
		width: 100%;
		display: flex;
		flex-direction: row;
		justify-content: space-evenly;
		align-items: center;
	}
	.card__inner-row {
		box-sizing: border-box;
		position: absolute;
		display: flex;
		flex-direction: column;
		justify-content: space-evenly;
		top: 25px;
		left: 10px;
		right: 10px;
		bottom: 25px;
	}
	.flex {
		display: flex;
		flex-wrap: wrap;
	}
	.card {
		position: relative;
		display: inline-block;
		width: 172px;
		height: 240px;
		background-image: url(/wood.jpg);
		border: solid 10px white;
		font-size: 16px;
		font-weight: 800;
		color: black;
		margin: 5px;
	}
	.card:before,
	.card:after {
		content: attr(value);
		position: absolute;
		width: 29px;
		height: 50px;
		text-align: center;
		background-color: white;
		border-radius: 0px 0px 12px 0px;
	}

	.card:after {
		bottom: 0;
		right: 0;
		transform: rotate(180deg);
	}
	.card--heart:before,
	.card--heart:after {
		content: attr(value) url("/abs.svg");
	}
	.card__inner {
		box-sizing: border-box;
		position: absolute;
		display: flex;
		justify-content: space-evenly;
		top: 25px;
		left: 25px;
		right: 25px;
		bottom: 25px;
	}
	.card__inner--center {
		align-items: center;
	}
	.card__column {
		display: flex;
		flex-direction: column;
		justify-content: space-between;
	}
	.card__column--centered {
		justify-content: center;
	}

	.card__symbol {
		display: inline-block;
		height: 40px;
		text-align: center;
		transform: scale(2);
	}
	.card__symbol:before {
		font-size: 37px;
		line-height: 37px;
	}

	.card--heart .card__symbol:before {
		content: url("/abs.svg");
	}
	.card__symbol--big {
		transform: scale(4);
	}
	.y-rotate {
		transform: rotate(180deg) scale(2);
	}
	.xy-rotate {
		transform: rotate(180deg) scaleX(-1) scale(2);
	}
	.x-rotate {
		transform: scaleX(-1) scale(2);
	}
</style>
