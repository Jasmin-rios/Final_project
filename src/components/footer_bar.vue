<script>
    export default {
        name: "footer_bar",
    }
</script>

<template>
    <section class="footer">
        <div class="all-options">
            <div class="footer-options">
                <p>Your Account</p>
                <ul>
                    <li>Log In</li>
                    <li>Sign Up</li>
                </ul>
            </div>
            <div class="footer-options">
                <p>Discover</p>
                <ul>
                    <li>Type of Events</li>
                    <li>Recommendations</li>
                    <li>More information</li>
                </ul>
            </div>
            <div class="footer-options">
                <p>LiviT</p>
                <ul>
                    <li>About Us</li>
                    <li>Newletter</li>
                </ul>
            </div>
        </div>
        <div class="footer-social-media">
            <div class="Follow-us">
                <p class="Follow-us-p">Follow us</p>
                <div id="icons-box">
                    <img class="icons" src="../assets/facebook.svg"/>
                    <img class="icons" src="../assets/instagram.svg"/>
                    <img class="icons" src="../assets/linkedin.svg">
                    <img class="icons" src="../assets/twitter.svg">
                </div>
            </div>
            <img id= "logo-footer" src="../assets/logo_blanco.svg"/>
        </div>
        <div id="copy">
            <p>&copy; 2023 LiviT. All rights reserved.</p>
        </div>
    </section>
</template>

<style scoped>
    .footer {
        display: flex;
        background-color: black;
        flex-direction: column;
    }
/* <<caja de arriba>> */
    .all-options {
        display: flex;
        gap: 50px;
        flex-wrap: wrap;
        justify-content: space-around;
        align-items: flex-start;
        flex-direction: row;
        width: 100%;
        height: 100%;
        margin: 0 auto;
        box-sizing: border-box;
        padding: 20px;
        
        
    }
    .footer-options {
        color: white;
        gap: 4px;
    }
    ul {
        list-style-type: none;
        padding-left: 0px;
        font-size: 16px;
    }

    p {
        font-style: normal;
        font-weight: 600;
        font-size: 20x;
        line-height: 24px;
    }

    /* <<caja de abajo>> */
    .footer-social-media {
        display: flex;
        gap: 360px;
        justify-content: space-around;
        margin: 0px auto;
        align-items:center;
        flex-direction: row;
        width: 100%;
        height: 100%;
        box-sizing: border-box;
        padding: 20px 20px;
    }

    .Follow-us {
        flex-direction: column;
        align-items: flex-start;
        padding: 0px;
        gap: 8px;
    }
    .Follow-us-p {
        color: white;
    }

    #icon-box {
        display: flex;
        flex-direction: row;
        align-items: flex-start;
        padding: 0px;
        gap: 100px;

        width: 232px;
        height: 40px;
    }
    .icons {
        width: 20px;
        height: 20px;
        padding: 6px;
    }

    #logo-footer {
        width: 150px;
        height: 50px;

    }
    #copy {
        color: white;
        padding: auto;
        margin: 0 auto;
        align-items: left;
        font-size: 12px;
    }
</style>