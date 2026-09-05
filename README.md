<script>

/* ==========================================
SUPABASE
========================================== */

const SUPABASE_URL = "ضع Project URL هنا";
const SUPABASE_KEY = "ضع Publishable key هنا";

let supabaseClient = null;

try {

    if (
        SUPABASE_URL.startsWith("https://") &&
        SUPABASE_KEY &&
        !SUPABASE_KEY.includes("ضع Publishable")
    ) {

        supabaseClient =
            window.supabase.createClient(
                SUPABASE_URL,
                SUPABASE_KEY
            );

    }

} catch(error) {

    console.error("Supabase error:", error);

}


/* ==========================================
ADMIN PASSWORD
========================================== */

const ADMIN_PASSWORD = "Espoza202900$";


/* ==========================================
LOGIN
========================================== */

function login(){

    const passwordInput =
        document.getElementById("password");

    const error =
        document.getElementById("loginError");

    const password =
        passwordInput.value.trim();

    error.textContent = "";

    if(password === ADMIN_PASSWORD){

        localStorage.setItem(
            "espoza_admin_logged",
            "true"
        );

        document
            .getElementById("loginPage")
            .classList.add("hidden");

        document
            .getElementById("adminPage")
            .classList.remove("hidden");

        loadDashboard();

    }else{

        error.textContent =
            "كلمة السر غير صحيحة ❌";

        passwordInput.value = "";
        passwordInput.focus();

    }

}


/* ==========================================
LOGOUT
========================================== */

function logout(){

    localStorage.removeItem(
        "espoza_admin_logged"
    );

    location.reload();

}


/* ==========================================
CHECK LOGIN
========================================== */

function checkLogin(){

    const logged =
        localStorage.getItem(
            "espoza_admin_logged"
        );

    if(logged === "true"){

        document
            .getElementById("loginPage")
            .classList.add("hidden");

        document
            .getElementById("adminPage")
            .classList.remove("hidden");

        loadDashboard();

    }

}


/* ==========================================
DASHBOARD
========================================== */

async function loadDashboard(){

    if(!supabaseClient){

        console.log(
            "Supabase غير مربوط حاليًا"
        );

        return;

    }

    try{

        const products =
            await supabaseClient
                .from("products")
                .select("id,is_offer");

        if(!products.error){

            document.getElementById(
                "productsCount"
            ).textContent =
                products.data.length;

            document.getElementById(
                "offersCount"
            ).textContent =
                products.data.filter(
                    p => p.is_offer === true
                ).length;

        }


        const orders =
            await supabaseClient
                .from("orders")
                .select("id");

        if(!orders.error){

            document.getElementById(
                "ordersCount"
            ).textContent =
                orders.data.length;

        }

    }catch(error){

        console.error(error);

    }

}


/* ==========================================
START
========================================== */

document.addEventListener(
    "DOMContentLoaded",
    function(){

        const password =
            document.getElementById("password");

        password.focus();

        checkLogin();

    }
);

</script>
