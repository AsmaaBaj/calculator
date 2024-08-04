<script lang="ts">
    import Backspace from "$lib/Icon/Backspace.svelte";
    import Division from "$lib/Icon/Division.svelte" ;
    import Multiply from "$lib/Icon/Multiply.svelte" ;
    import Minus from "$lib/Icon/Minus.svelte"
    import Plus from "$lib/Icon/Plus.svelte";
    import Equal from "$lib/Icon/Equal.svelte";
    import Percent from "$lib/Icon/Percent.svelte";

    let equation: String ="";

    function addToEquatoin(value:string){
        equation+=value;
    }
    
    function BackSpace(){
       equation=equation.substring(0, equation.length-1);
    }

    function clear(){
     equation="";
    }

    function solve(){
        equation = eval(equation);
    }
</script>

<svelte:head>
    <title>
        calculator
    </title>
</svelte:head>
         

    <div class="  bg-white rounded-3xl grid grid-cols-4 gap-1 p-3 border-4 border-[#7e7d39b0] 
    font-semibold shadow-2xl ">
        <div class="bg-[#fffb1ebb] rounded-full col-span-4 h-12 flex items-center px-3 
        mb-2 border-[3px] border-[#7e7d3974]"> {equation} </div>
        <button class="bg-slate-500 text-xl" on:click={()=>addToEquatoin(" / 100")}>
            <Percent/>
         </button>

        <button class="bg-slate-500 text-xl" on:click={BackSpace}>
           <Backspace/>
        </button>
        
        <button class="bg-red-700 text-white col-span-2" on:click={()=>clear()}>C</button>

        <button on:click={()=> addToEquatoin('7')} >7</button>
        <button on:click={()=> addToEquatoin('8')}>8</button>
        <button on:click={()=> addToEquatoin('9')}>9</button>
        <button class="bg-[#7e7d39b0] text-3xl" on:click={()=> addToEquatoin(' - ')}>
           <Minus/>
        </button>

        <button on:click={()=> addToEquatoin('4')}>4</button>
        <button on:click={()=> addToEquatoin('5')}>5</button>
        <button on:click={()=> addToEquatoin('6')}>6</button>
        <button class="bg-[#fffb1e] text-3xl" on:click={()=> addToEquatoin(' / ')}>
            <Division/>
        </button>

        <button on:click={()=> addToEquatoin('1')}>1</button>
        <button on:click={()=> addToEquatoin('2')}>2</button>
        <button on:click={()=> addToEquatoin('3')}>3</button>
        <button class="bg-[#7e7d39b0] text-2xl"  on:click={()=> addToEquatoin(' * ')}>
            <Multiply/>
        </button>

        <button on:click={()=> addToEquatoin('.')}>.</button>
        <button on:click={()=> addToEquatoin('0')}>0</button>
        <button class="bg-slate-500 text-xl" on:click={()=> solve()}>
            <Equal/>
        </button>
        <button class="bg-[#fffb1e] text-2xl" on:click={()=> addToEquatoin(' + ')}>
            <Plus/>
        </button>

    </div>
  
