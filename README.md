<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pet Adoption</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f9f9f9;
            color: #333;
        }

        header {
            background-color: #4CAF50;
            color: white;
            padding: 1rem 0;
            text-align: center;
        }

        .container {
            max-width: 900px;
            margin: 2rem auto;
            padding: 1rem;
            background: white;
            border-radius: 8px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        }

        h2 {
            color: #4CAF50;
        }

        .pet-types {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 1rem;
        }

        .pet-card {
            border: 1px solid #ddd;
            border-radius: 8px;
            padding: 1rem;
            text-align: center;
        }

        .pet-card img {
            max-width: 100%;
            border-radius: 8px;
        }

        .adoption-form {
            margin-top: 2rem;
        }

        form {
            display: flex;
            flex-direction: column;
            gap: 1rem;
        }

        input, select, textarea, button {
            padding: 0.5rem;
            border: 1px solid #ccc;
            border-radius: 4px;
            font-size: 1rem;
        }

        button {
            background-color: #4CAF50;
            color: white;
            border: none;
            cursor: pointer;
        }

        button:hover {
            background-color: #45a049;
        }
    </style>
</head>
<body>
    <header>
        <h1>Welcome to the Pet Adoption Center</h1>
        <p>Find your perfect furry friend today!</p>
    </header>

    <div class="container">
        <section>
            <h2>Types of Pets Available</h2>
            <div class="pet-types">
                <div class="pet-card">
                    <img src="https://imgs.search.brave.com/Ke731q2vM4wOTQ752CUbmnFbVTIHQsVFNTlEJxmq8bM/rs:fit:860:0:0:0/g:ce/aHR0cHM6Ly9zdGF0/aWMuYm9yZWRwYW5k/YS5jb20vYmxvZy93/cC1jb250ZW50L29y/Z191cGxvYWRzLzIw/MTQvMDYvbm9uZTI5/MDdfXzcwMC5qcGc" alt="Dog">
                    <h3>Dogs</h3>
                    <p>Friendly, loyal, and full of energy. Perfect for families and active individuals.</p>
                </div>
                <div class="pet-card">
                    <img src="https://imgs.search.brave.com/1dZJIDO8_i6AbEyyf1SPmzI-T5EbGvAXKJexpoTOQsk/rs:fit:860:0:0:0/g:ce/aHR0cHM6Ly93YWxs/cGFwZXJzLmNvbS9p/bWFnZXMvZmVhdHVy/ZWQvY29vbC1jYXQt/cGljdHVyZXMtYWxq/c2VoMXl4OGxmM2Ji/cC5qcGc" alt="Cat">
                    <h3>Cats</h3>
                    <p>Independent and loving. Ideal for those looking for a low-maintenance companion.</p>
                </div>
                <div class="pet-card">
                    <img src="https://imgs.search.brave.com/txnvlcYuC5L44h1s-mj839mU3D_A_lKz_2nNtsCbX1w/rs:fit:860:0:0:0/g:ce/aHR0cHM6Ly93YWxs/cGFwZXJzLmNvbS9p/bWFnZXMvaGQvY3V0/ZS1idW5ueS1hdC1o/b21lLXBpY3R1cmUt/NDhyaGZpbGw4MTVs/ZHIxcC5qcGc" alt="Rabbit">
                    <h3>Rabbits</h3>
                    <p>Gentle and quiet. Great for smaller homes and first-time pet owners.</p>
                </div>
            </div>
        </section>

        <section class="adoption-form">
            <h2>Adoption Form</h2>
            <form action="#" method="POST">
                <label for="name">Your Name:</label>
                <input type="text" id="name" name="name" placeholder="Enter your full name" required>

                <label for="email">Email Address:</label>
                <input type="email" id="email" name="email" placeholder="Enter your email" required>

                <label for="phone">Phone Number:</label>
                <input type="tel" id="phone" name="phone" placeholder="Enter your phone number" required>

                <label for="pet">Select a Pet Type:</label>
                <select id="pet" name="pet" onchange="showBreedOptions(this.value)">
                    <option value="">--Select Pet--</option>
                    <option value="dog">Dog</option>
                    <option value="cat">Cat</option>
                    <option value="rabbit">Rabbit</option>
                </select>

                <div id="breed-section">
                    <label for="breed">Select a Breed:</label>
                    <select id="breed" name="breed">
                        <option value="">-- Please select a pet type first --</option>
                    </select>
                </div>

                <label for="experience">Do you have prior pet experience?</label>
                <div>
                    <input type="radio" id="yes" name="experience" value="yes">
                    <label for="yes">Yes</label>
                    <input type="radio" id="no" name="experience" value="no">
                    <label for="no">No</label>
                </div>

                <label for="reason">Why do you want to adopt a pet?</label>
                <textarea id="reason" name="reason" rows="4" placeholder="Write a brief reason here..." required></textarea>

                <label>
                    <input type="checkbox" name="agree" required> I agree to the terms and conditions.
                </label>

                <button type="submit">Submit Application</button>
            </form>
        </section>
    </div>

    <script>
        function showBreedOptions(petType) {
            const breedSelect = document.getElementById('breed');
            breedSelect.innerHTML = '';

            let breeds = [];
            if (petType === 'dog') {
                breeds = ['--Select Breed--', 'Labrador', 'German Shepherd', 'Bulldog', 'Golden Retriever'];
            } else if (petType === 'cat') {
                breeds = ['--Select Breed--', 'Persian', 'Siamese', 'Maine Coon', 'Ragdoll'];
            } else if (petType === 'rabbit') {
                breeds = ['--Select Breed--', 'Lionhead', 'Dutch', 'Mini Lop', 'Flemish Giant'];
            }

            if (breeds.length > 0) {
                breeds.forEach(breed => {
                    const option = document.createElement('option');
                    option.value = breed.toLowerCase();
                    option.textContent = breed;
                    breedSelect.appendChild(option);
                });
            } else {
                const option = document.createElement('option');
                option.value = '';
                option.textContent = '-- Please select a pet type first --';
                breedSelect.appendChild(option);
            }
        }
    </script>
</body>
</html>
