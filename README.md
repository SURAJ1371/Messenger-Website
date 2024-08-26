# Messenger-Website
Can be used to send messages on whatsapp as well as instagram without visiting them separately but in one go and simultaneously. Just send message to one messenger and your message will be send to both social media.

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Messenger App</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha3/dist/css/bootstrap.min.css" rel="stylesheet">
</head>
<body>
    <div class="container mt-5">
        <h1 class="text-center">Messenger App</h1>

        <form id="messageForm">
            <div class="mb-3">
                <label for="whatsapp" class="form-label">WhatsApp Number</label>
                <input type="text" class="form-control" id="whatsapp" placeholder="Enter number with country code" required>
            </div>
            <div class="mb-3">
                <label for="instagram" class="form-label">Instagram Username</label>
                <input type="text" class="form-control" id="instagram" placeholder="Enter Instagram username" required>
            </div>
            <div class="mb-3">
                <label for="message" class="form-label">Message</label>
                <textarea class="form-control" id="message" rows="3" placeholder="Enter your message" required></textarea>
            </div>
            <button type="submit" class="btn btn-primary w-100">Send Message</button>
        </form>

        <div id="response" class="mt-3 text-center"></div>
    </div>

    <script>
        document.getElementById('messageForm').addEventListener('submit', function (event) {
            event.preventDefault(); // Prevent form from submitting

            const whatsappNumber = document.getElementById('whatsapp').value;
            const instagramUsername = document.getElementById('instagram').value;
            const message = encodeURIComponent(document.getElementById('message').value); // Encode the message for URL

            // Open WhatsApp
            if (whatsappNumber) {
                const whatsappURL = `https://wa.me/${whatsappNumber}?text=${message}`;
                window.open(whatsappURL, '_blank');
            }

            // Open Instagram profile in a new tab
            if (instagramUsername) {
                const instagramURL = `https://www.instagram.com/${instagramUsername}/`;
                window.open(instagramURL, '_blank');
            }
        });
    </script>
</body>
</html>


    
        
       

           
           

  

