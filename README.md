# Messenger-Website
Can be used to send messages on whatsapp as well as instagram without visiting them separately but in one go and simultaneously. Just send message to one messenger and your message will be send to both social media.

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Charming Messenger App</title>
    <style>
        /* General Body Style */
        body {
            font-family: 'Poppins', sans-serif;
            background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            color: #333;
        }

        /* Container for the Form */
        .container {
            background-color: white;
            border-radius: 12px;
            box-shadow: 0 15px 25px rgba(0, 0, 0, 0.2);
            padding: 30px;
            width: 350px;
            max-width: 100%;
            text-align: center;
            position: relative;
        }

        /* Title Style */
        h1 {
            font-size: 2.2em;
            margin-bottom: 10px;
            color: #f5576c;
            font-weight: 600;
        }

        /* Input and Textarea Style */
        input, textarea {
            width: 100%;
            padding: 10px;
            margin-bottom: 20px;
            border: none;
            border-radius: 8px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
            font-size: 1em;
            transition: box-shadow 0.3s ease;
        }

        /* On focus effect for Input and Textarea */
        input:focus, textarea:focus {
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.3);
            outline: none;
        }

        /* Button Style */
        button {
            background-color: #f5576c;
            color: white;
            padding: 12px;
            border: none;
            border-radius: 8px;
            font-size: 1.2em;
            font-weight: bold;
            cursor: pointer;
            transition: background-color 0.3s ease, transform 0.2s ease;
            width: 100%;
        }

        /* Hover effect for the button */
        button:hover {
            background-color: #d04556;
            transform: translateY(-2px);
        }

        /* Custom Input Labels */
        label {
            font-weight: bold;
            color: #555;
            display: block;
            text-align: left;
            margin-bottom: 5px;
        }

        /* Form Control Style */
        form {
            margin-top: 20px;
        }

        /* Animation for subtle charm */
        .container::before {
            content: '';
            position: absolute;
            width: 150px;
            height: 150px;
            background: rgba(255, 255, 255, 0.2);
            top: -50px;
            right: -50px;
            border-radius: 50%;
            filter: blur(100px);
            z-index: -1;
        }

        .container::after {
            content: '';
            position: absolute;
            width: 200px;
            height: 200px;
            background: rgba(255, 255, 255, 0.1);
            bottom: -60px;
            left: -60px;
            border-radius: 50%;
            filter: blur(150px);
            z-index: -1;
        }
    </style>
</head>
<body>

    <div class="container">
        <h1>Send a Message</h1>
        <form id="messageForm">
            <label for="whatsapp">WhatsApp Number:</label>
            <input type="text" id="whatsapp" name="whatsapp" placeholder="Enter WhatsApp number (with country code)" required>

            <label for="instagram">Instagram Username:</label>
            <input type="text" id="instagram" name="instagram" placeholder="Enter Instagram username" required>

            <label for="message">Message:</label>
            <textarea id="message" name="message" rows="4" placeholder="Type your message" required></textarea>

            <button type="button" onclick="sendToSocials()">Send Message</button>
        </form>
    </div>

    <script>
        function sendToSocials() {
            const whatsappNumber = document.getElementById('whatsapp').value;
            const instagramUsername = document.getElementById('instagram').value;
            const message = encodeURIComponent(document.getElementById('message').value);

            // WhatsApp Redirection
            if (whatsappNumber) {
                const whatsappURL = `https://api.whatsapp.com/send?phone=${whatsappNumber}&text=${message}`;
                window.open(whatsappURL, '_blank');
            }

            // Instagram Redirection
            if (instagramUsername) {
                const instagramURL = `https://www.instagram.com/${instagramUsername}`;
                window.open(instagramURL, '_blank');
            }
        }
    </script>

</body>
</html>
