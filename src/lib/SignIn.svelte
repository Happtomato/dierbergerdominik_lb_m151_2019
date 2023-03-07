<script lang="ts">
    import { initializeApp } from "firebase/app";
    import { getAuth } from "Firebase/auth";
    import { signInWithEmailAndPassword } from "Firebase/auth";

    const firebaseConfig = {
        apiKey: "AIzaSyADxhEkmy3jeQMsLbwLDkNGK_cca5X10bw",
        authDomain: "futurelog-worktime-calculator.firebaseapp.com",
        projectId: "futurelog-worktime-calculator",
        storageBucket: "futurelog-worktime-calculator.appspot.com",
        messagingSenderId: "88187511821",
        appId: "1:88187511821:web:9952141217c03eccbb2144"
    };

    let email = "";
    let password = "";
    let errorBool = false;
    async function signIn(event) {
        try {
            let user = await signInWithEmailAndPassword(auth, event.detail.email, event.detail.password)
        } catch (error) {
            console.log("error signin in", error.message)
            error = error.message
            errorBool = true;
        }
    }


</script>

<div class="min-h-screen py-6 flex flex-col justify-center sm:py-12">
    <div class="relative py-3 sm:max-w-xl sm:mx-auto">
        <div
                class="absolute inset-0 bg-gradient-to-r from-orange-300 to-orange-600 shadow-lg transform -skew-y-6 sm:skew-y-0 sm:-rotate-6 sm:rounded-3xl">
        </div>
        <div class="relative px-4 py-10 bg-white shadow-lg sm:rounded-3xl sm:p-20">
            <div class="max-w-md mx-auto">
                <h1 class="text-2xl font-semibold">Login to worktime calculator</h1>
                <div class="divide-y divide-gray-200">
                    <div class="py-8 text-base leading-6 space-y-4 text-gray-700 sm:text-lg sm:leading-7">
                        <div class="relative">
                            <input bind:value={email} autocomplete="off" id="email" name="email" type="text" class="peer placeholder-transparent h-10 w-full rounded-md border-b-2 border-gray-300 text-gray-900 focus:outline-none focus:border-orange-600" placeholder="Email address" />
                            <label for="email" class="absolute left-3 -top-5 text-gray-600 text-sm peer-placeholder-shown:text-base peer-placeholder-shown:text-gray-440 peer-placeholder-shown:top-2 transition-all peer-focus:-top-5 peer-focus:text-gray-600 peer-focus:text-sm">Email Address</label>
                        </div>
                        <div class="relative">
                            <input bind:value={password} autocomplete="off" id="password" name="password" type="password" class="peer placeholder-transparent h-10 w-full rounded-md border-b-2 border-gray-300 text-gray-900 focus:outline-none focus:border-orange-600" placeholder="Password" />
                            <label for="password" class="absolute left-3 -top-5 text-gray-600 text-sm peer-placeholder-shown:text-base peer-placeholder-shown:text-gray-440 peer-placeholder-shown:top-2 transition-all peer-focus:-top-5 peer-focus:text-gray-600 peer-focus:text-sm">Password</label>
                        </div>
                        <div class="relative">
                            <button on:click={signIn()} class="bg-blue-500 text-white rounded-md px-3 py-1 mt-2 mb-5">Sign In</button>
                            <br>
                            <p class="text-sm inline">No account?</p> <a class="text-sm inline text-orange-600" href="*">Sign Up instead</a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</div>
