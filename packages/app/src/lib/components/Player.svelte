<div class="player_block">
	<div class="player_name">
		<span>Al Pudding</span>
	</div>
	<div class="player_info">
		<div class="player_image" />
		<div class="card_count">
			<div class="card">6</div>
			<div class="card_before" />
		</div>
	</div>
</div>

<style>
	.player_block {
		width: 230px;
	}
	.player_name {
		width: inherit;
		line-height: 30px;
		font-weight: 600;
		font-size: 20px;
		background: linear-gradient(
			90deg,
			rgba(0, 212, 255, 0.5102415966386555) 80%,
			rgba(0, 212, 255, 0) 100%
		);
		border-radius: 8px;
	}
	.player_name span {
		padding-left: 12px;
		text-shadow: 2px 2px 4px #000000;
	}
	.player_info {
		display: flex;
		align-items: flex-end;
		justify-content: flex-end;
	}
	.player_image {
		margin-top: 10px;
		background-image: url("https://i.pinimg.com/originals/72/69/f5/7269f5aef4e6aed9bebe0a5c6808b06e.jpg");
		background-size: cover;
		background-position: 50% 50%;
		width: 150px;
		height: 150px;
		border-radius: 20%;
	}
	.card {
		position: absolute;
		width: 26px;
		height: 35px;
		bottom: 0;
		left: 7;
		display: flex;
		justify-content: center;
		align-items: center;
		color: black;
		font-size: 25px;
		font-weight: 800;
		border: solid 2px black;
		background-color: white;
		box-shadow: 0 0 10px rgba(255, 255, 255, 0.5);
	}
	.card_before {
		border: solid 2px black;
		position: absolute;
		width: 26px;
		height: 35px;
		background-color: white;
		bottom: 8px;
		left: -8px;
		z-index: -1;
		box-shadow: 0 0 10px rgba(255, 255, 255, 0.5);
	}
	.card_count {
		width: 52px;
		position: relative;
		margin-left: 15px;
		margin-bottom: 15px;
	}
</style>
