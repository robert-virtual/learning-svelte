<script>
import { createEventDispatcher } from "svelte"
const dispatch = createEventDispatcher()
let name = ""
let age = 0
let showText = true
function sayHello() {
   dispatch('message',{
       text:"Hola"
   }) 
}
let flavours = []
let menu = [
	'Cookies and cream',
	'Mint choc chip',
	'Raspberry ripple'
];
</script>
<h2>Flavours </h2>
<p>{flavours.join(",")}</p>
{#each menu as flavour}
	<label>
		<input type=checkbox bind:group={flavours} name="flavours" value={flavour}>
		{flavour}
	</label>
{/each}
<hr>
<h2>{name}</h2>
<h2>{age}</h2>
<input type="text" bind:value={name}>
<input type="number" bind:value={age}>
<br>
<label for="showText">Show Text</label>
<input type="checkbox"  id="showText" bind:checked={showText}>
<br>
{#if showText}
<p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Nemo eaque, libero molestias ut, ratione corrupti illum harum enim officia nostrum iste velit quidem corporis soluta perspiciatis id aperiam. Nostrum facere optio quibusdam molestiae voluptates, cum aperiam, tempora cupiditate rem obcaecati corporis doloremque, maiores fuga expedita? Optio perferendis illo, reiciendis asperiores cumque blanditiis. Quo nesciunt officia porro asperiores commodi, cumque ullam, quae iste minima, labore non. Hic excepturi nesciunt facilis, accusamus, ipsam culpa minus voluptatibus aperiam fuga qui quisquam enim natus quam quis mollitia minima officiis consequuntur at velit ut, sapiente possimus. Perspiciatis laudantium sed recusandae quas consequuntur totam qui quis laborum. Cum voluptatibus numquam consequuntur labore ex fugiat alias ea, ad quibusdam corporis quasi. Ipsum accusamus, aliquam ratione debitis ab enim consectetur atque a! Fuga esse delectus dolore hic at nobis, autem dignissimos nostrum architecto? Quae ipsum, similique temporibus sunt tempora explicabo doloribus numquam commodi perferendis repudiandae rerum, exercitationem corporis.</p>
{/if}
<button on:click={sayHello}>click to say hello</button>