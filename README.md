# Messenger-Website
Can be used to send messages on whatsapp as well as instagram without visiting them separately but in one go and simultaneously. Just send message to one messenger and your message will be send to both social media.

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Messenger Website</title>
    
    <!-- Bootstrap CSS -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha3/dist/css/bootstrap.min.css" rel="stylesheet">

    <!-- Font Awesome for Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">

    <style>
        body {
            background-color: #f8f9fa;
            font-family: 'Arial', sans-serif;
        }

        .messenger-container {
            max-width: 600px;
            margin: 50px auto;
            background-color: white;
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0px 0px 30px rgba(0, 0, 0, 0.1);
        }

        .messenger-title {
            text-align: center;
            font-size: 2rem;
            color: #495057;
            margin-bottom: 30px;
            font-weight: bold;
        }

        .form-control {
            margin-bottom: 20px;
            padding: 15px;
            border-radius: 10px;
        }

        .form-control:focus {
            border-color: #007bff;
            box-shadow: 0 0 10px rgba(0, 123, 255, 0.2);
        }

        .btn-send {
            background-color: #007bff;
            color: white;
            border-radius: 50px;
            padding: 10px 30px;
            font-size: 1.2rem;
            transition: background-color 0.3s ease;
        }

        .btn-send:hover {
            background-color: #0056b3;
        }

        .icon-wrapper {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 20px;
        }

        .icon-wrapper i {
            font-size: 2.5rem;
            color: #007bff;
            transition: color 0.3s ease;
        }

        .icon-wrapper i:hover {
            color: #0056b3;
        }

        /* Media Queries for Mobile Responsiveness */
        @media (max-width: 768px) {
            .messenger-container {
                padding: 20px;
            }

            .messenger-title {
                font-size: 1.8rem;
            }
        }
    </style>
</head>
<body>

    <div class="messenger-container shadow-lg">
        <h1 class="messenger-title">Messenger App</h1>

        <!-- Form for WhatsApp and Instagram Message -->
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

            <button type="submit" class="btn btn-send w-100">Send Message</button>
        </form>

        <!-- Icons for WhatsApp and Instagram -->
        <div class="icon-wrapper">
            <i class="fab fa-whatsapp"></i>
            <i class="fab fa-instagram"></i>
        </div>
    </div>

    <!-- Bootstrap JS and Popper -->
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha3/dist/js/bootstrap.bundle.min.js"></script>

    <!-- JavaScript Logic -->
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

            // Open Instagram (DM link not available, so we provide a profile link instead)
            if (instagramUsername) {
                const instagramURL = `https://www.instagram.com/${instagramUsername}/`;
                alert("Instagram does not allow automated messages from the web. You will be redirected to the profile.");
                window.open(instagramURL, '_blank');
            }
        });
    </script>

</body>
</html>
