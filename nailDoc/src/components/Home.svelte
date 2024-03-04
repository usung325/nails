<script>
    let rows = [1,2,3];

    let is_ctrl_down = false;
    let is_h_down = false;
    let currActive = false;
    let currW = false;


    let down3 = false;
    let curr3 = false;

    let down4 = false;
    let curr4 = false;

    let down8 = false;
    let curr8 = false;

    let down9 = false;
    let curr9 = false;

    let downQ = false;
    let currQ = false;

    let downR = false;
    let currR = false;

    let downV = false;
    let currV = false;

    let downN = false;
    let currN = false;

    let downU = false;
    let currU = false;

    let downP = false;
    let currP = false;

    function on_bind(keyP){
        console.log("its working");
        currActive = true;

        if (keyP == 3){
            curr3 = true;
        }

        if (keyP == 4){
            curr4 = true;
        }

        if (keyP == q){
            currQ = true;
        }

        // else if (keyP == r){
        //     currR = true;
        // }

        // else if (keyP == v){
        //     currV = true;
        // }

        // else if (keyP == n){
        //     currN = true;
        // }

        // else if (keyP == u){
        //     currU = true;
        // }

        // else if (keyP == p){
        //     currP = true;
        // }

        
    }

    function release_bind(keyP){
        currActive = false;


        if (keyP == 3){
            curr3 = false;
        }
        if (keyP == 4){
            curr4 = false;
        }

        // if (keyP == q){
        //     currQ = false;
        // }

        // else if (keyP == r){
        //     currR = false;
        // }

        // else if (keyP == v){
        //     currV = false;
        // }

        // else if (keyP == n){
        //     currN = false;
        // }

        // else if (keyP == u){
        //     currU = false;
        // }

        // else if (keyP == p){
        //     currP = false;
        // }
    }

    function on_key_down(event){
        if (event.repeat) return;

        switch(event.key){
            case "Control":
                is_ctrl_down = true;

                event.preventDefault();
                break;
            case "s":
                is_h_down = true;

                event.preventDefault();
                break;

            case "3":
                down3 = true;

                event.preventDefault();
                break;

            case "4":
                down4 = true;

                event.preventDefault();
                break;

            case "q":
                downQ = true;

                event.preventDefault();
                break;

            // case "r":
            //     downR = true;

            //     event.preventDefault();
            //     break;

            // case "v":
            //     downV = true;

            //     event.preventDefault();
            //     break;

            // case "n":
            //     downN = true;

            //     event.preventDefault();
            //     break;
            
            // case "u":
            //     downU = true;

            //     event.preventDefault();
            //     break;

            // case "p":
            //     downP = true;

            //     event.preventDefault();
            //     break;
        }

        if (is_ctrl_down && is_h_down) {
            on_bind();
        }

        else if (down3){
            on_bind(3);
        }

        else if (down4){
            on_bind(4);
        }

        else if (downQ){
            on_bind(q);
        }

        // else if (downR){
        //     on_bind(r);
        // }

        // else if (downV){
        //     on_bind(v);
        // }

        // else if (downN){
        //     on_bind(n);
        // }

        // else if (downU){
        //     on_bind(u);
        // }

        // else if (downP){
        //     on_bind(p);
        // }
        // else if (down8){
        //     on_bind(8);
        // }
        // else if (down9){
        //     on_bind(9);
        // }

    }

    function on_key_up(event){
        switch (event.key){
            case "Control":
                is_ctrl_down = false;

                event.preventDefault();
                break;

            case "s":
                is_h_down = false;

                event.preventDefault();
                break;

            case "3":
                down3 = false;

                event.preventDefault();
                break;

            case "4":
                down4 = false;

                event.preventDefault();
                break;

            case "q":
                downQ = false;

                event.preventDefault();
                break;

            // case "r":
            //     downR = false;

            //     event.preventDefault();
            //     break;

            // case "v":
            //     downV = false;

            //     event.preventDefault();
            //     break;

            // case "n":
            //     downN = false;

            //     event.preventDefault();
            //     break;
            
            // case "u":
            //     downU = false;

            //     event.preventDefault();
            //     break;

            // case "p":
            //     downP = false;

            //     event.preventDefault();
            //     break;

        }

        if (is_ctrl_down == false || is_h_down == false) {
            release_bind();
        }

        if (down3 == false){
            release_bind(3);
        }

        if (down4 == false){
            release_bind(4);
        }

        else if (downQ == false){
            release_bind(q);
        }

        // // else if (downR == false){
        // //     release_bind(r);
        // // }

        // // else if (downV == false){
        // //     release_bind(v);
        // // }

        // // else if (downN == false){
        // //     release_bind(n);
        // // }

        // // else if (downU == false){
        // //     release_bind(u);
        // // }

        // // else if (down8 == false){
        // //     release_bind(8);
        // // }

        // // else if (down9 == false){
        // //     release_bind(9);
        // // }

        // // else if (downP == false){
        // //     release_bind(p);
        // // }

    }
    
</script>

<svelte:window
  on:keydown={on_key_down}
  on:keyup={on_key_up}
/>

<body class="p-11 mt-40">
    <div class="  ">
    
        <div class="grid grid-cols-10 items-center  -slate-600 text-center">
            <div class="bg-black">
                <p>:)</p>
            </div>

            
            {#if curr3} 
                <div class="bg-green-500 animate-bounce hover:bg-pink-500 transition duration-700 ease-in-out ">
                    <p class="animate-pulse ">3</p>
                </div>
            {:else}
                <div class="bg-green-500  hover:bg-pink-500 transition duration-700 ease-in-out ">
                    <p class=" ">3</p>
                </div>
            {/if}
            
            {#if curr4} 
                <div class="bg-green-500 animate-bounce hover:bg-pink-500 transition duration-700 ease-in-out ">
                    <p class="animate-pulse ">4</p>
                </div>
            {:else}
                <div class="bg-green-500  hover:bg-pink-500 transition duration-700 ease-in-out ">
                    <p class=" ">4</p>
                </div>
            {/if}

            <div class="bg-black">
                <p>:)</p>
            </div>

            <div class="bg-black">
                <p>:)</p>
            </div>
            <div class="bg-black">
                <p>:)</p>
            </div>
            <div class="bg-black">
                <p>:)</p>
            </div>

            <div class="bg-green-500">
                <p>8</p>
            </div>

            <div class="bg-green-500">
                <p>9</p>
            </div>
            <div class="bg-black">
                <p>:)</p>
            </div>
        </div>

    </div>

    <!--  -------------------------------------------------------------------------- -->
    <!--  -------------------------------------------------------------------------- -->
    <!--  -------------------------------------------------------------------------- -->
    <!--  -------------------------------------------------------------------------- -->


    <div class="  ">

        <div class="grid grid-cols-10 -slate-600 text-center items-center">
            {#if currQ} 
                <div class="bg-green-500 animate-bounce hover:bg-pink-500 transition duration-700 ease-in-out ">
                    <p class="animate-pulse ">Q</p>
                </div>
            {:else}
                <div class="bg-green-500  hover:bg-pink-500 transition duration-700 ease-in-out ">
                    <p class=" ">Q</p>
                </div>
            {/if}

            <div class="bg-black text-white">
                <h1>2</h1>
            </div>
            <div class="bg-black text-white">
                <h1>3</h1>
            </div>

            <div class="bg-green-500">
                <p>R</p>
            </div>

            <div class="bg-black">
                <p>:)</p>
            </div>
            <div class="bg-black">
                <p>:)</p>
            </div>
            <div class="bg-green-500">
                <p>U</p>
            </div>

            <div class="bg-black text-white">
                <h1> 8 </h1>
            </div>

            <div class="bg-black text-white">
                <h1> 9 </h1>
            </div>
            <div class="bg-green-500">
                <p>P</p>
            </div>
        </div>

    </div>
    
    <!--  -------------------------------------------------------------------------- -->
    <!--  -------------------------------------------------------------------------- -->
    <!--  -------------------------------------------------------------------------- -->
    <!--  -------------------------------------------------------------------------- -->


    <div class="  ">

        <div class="grid grid-cols-10 items-center  -slate-600 text-center">
            <div class="bg-black text-white">
                <h1>1</h1>
            </div>

            <div class="bg-black">
                <p>:)</p>
            </div>
            <div class="bg-black">
                <p>:)</p>
            </div>

            <div class="bg-black text-white">
                <h1>4</h1>
            </div>

            <div class="bg-black">
                <p>:)</p>
            </div>
            <div class="bg-black">
                <p>:)</p>
            </div>
            <div class="bg-black text-white">
                <h1>7</h1>
            </div>

            <div class="bg-black">
                <p>:)</p>
            </div>

            <div class="bg-black">
                <p>:)</p>
            </div>
            <div class="bg-black text-white">
                <h1>10</h1>
            </div>
        </div>

    </div>
    <!--  -------------------------------------------------------------------------- -->
    <!--  -------------------------------------------------------------------------- -->
    <!--  -------------------------------------------------------------------------- -->
    <!--  -------------------------------------------------------------------------- -->


    <div class="">

        <div class="grid grid-cols-10 items-center  text-center">
            <div class="bg-black">
                <p>:)</p>
            </div>

            <div class="bg-black">
                <p>:)</p>
            </div>
            <div class="bg-black">
                <p>:)</p>
            </div>

            <div class="bg-black">
                <p>:)</p>
            </div>

            <div class="bg-green-500">
                <p>V</p>
            </div>
            <div class="bg-green-500">
                <p>N</p>
            </div>
            <div class="bg-black">
                <p>:)</p>
            </div>

            <div class="bg-black">
                <p>:)</p>
            </div>

            <div class="bg-black">
                <p>:)</p>
            </div>
            <div class="bg-black">
                <p>:)</p>
            </div>
        </div>

    </div>

    <!--  -------------------------------------------------------------------------- -->
    <!--  -------------------------------------------------------------------------- -->
    <!--  -------------------------------------------------------------------------- -->
    <!--  -------------------------------------------------------------------------- -->


    <div class="">

        <div class="grid grid-cols-10 items-center  text-center">
            <div class="bg-black">
                <p>:)</p>
            </div>

            <div class="bg-black">
                <p>:)</p>
            </div>
            <div class="bg-black">
                <p>:)</p>
            </div>

            <div class="bg-black">
                <p>:)</p>
            </div>

            <div class="bg-black text-white">
                <h1>5</h1>
            </div>
            <div class="bg-black text-white">
                <h1>6</h1>
            </div>
            <div class="bg-black">
                <p>:)</p>
            </div>

            <div class="bg-black">
                <p>:)</p>
            </div>

            <div class="bg-black">
                <p>:)</p>
            </div>
            <div class="bg-black">
                <p>:)</p>
            </div>
        </div>

    </div>
    
<!--     
    <div class="w-full height-auto">
        <div class="bg-cyan-200">
            <div class="grid grid-rows-2 grid-flow-col gap-4">
                <p class="text-cyan-500">What is uys</p>
                <p> what</p>
            </div>
    
        </div>
    </div> -->
    <div class="bg-white my-10 py-2 w-[40%] mx-auto">
        <div class="flex justify-around">
            <h1 class=""> 2479 for <span class="text-green-500 text-decoration underline"> archive </span></h1>
        </div>
    </div>
    <div class="bg-white my-10 py-2 w-[40%] mx-auto">
        <div class="flex justify-around items-center">
            <h1 class=""> 5629 for <span class="text-green-500 text-decoration underline"> about </span></h1>
        </div>
    </div>

</body>