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
        <!-- <div class="footer-social-media">
            <div id="Follow-us">
                <p>Follow us</p>
                <div id="icons-box">
                    <img src="../assets/facebook.svg"/>
                    <img src="../assets/instagram.svg"/>
                    <img src="../assets/linkedin.svg">
                    <img src="../assets/twitter.svg">
                </div>
            </div>
            <img id= "logo-footer" src="../assets/Logo.png"/>
        </div> -->
    </section>
</template>

<style scoped>
    .footer {
        display: flex;
        background-color: black;
    }

    .all-options {
        display: flex;
        gap: 50px;
        flex-wrap: wrap;
        justify-content: space-around;
        margin: 10px auto;
        align-items: flex-start;
        flex-direction: row;
        width: 90%;
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

</style>