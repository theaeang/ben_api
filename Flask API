from flask import Flask, jsonify
import os  # <-- IMPORTANT: Import os

app = Flask(__name__)

# Your emergency numbers data
emergency_data = {
    "police": [
        {"name": "Baguio City Police Office (BCPO) - Main", "number": "(074) 442-1211 or 911"},
        {"name": "Police Station 1 (Naguilian Rd)", "number": "(074) 442-6527"},
        {"name": "Police Station 2 (Camdas)", "number": "(074) 442-4322"},
        {"name": "Police Station 3 (Pacdal)", "number": "(074) 442-2438"},
        {"name": "Police Station 4 (Loakan)", "number": "(074) 444-9866"},
        {"name": "Police Station 5 (Legarda)", "number": "(074) 445-0454"},
        {"name": "Police Station 6 (Aurora Hill)", "number": "(074) 442-7433"},
        {"name": "Police Station 7 (Abanao St)", "number": "(074) 619-2210"},
        {"name": "Police Station 8 (Kennon Rd)", "number": "(074) 445-0453"},
        {"name": "Police Station 9 (Irisan)", "number": "(074) 424-2223"},
        {"name": "Police Station 10 (Marcos Highway)", "number": "(074) 424-2224"}
    ],
    "medical": [
        {"name": "Baguio General Hospital (BGHMC)", "number": "(074) 442-4018 or 911"},
        {"name": "SLU Hospital of the Sacred Heart", "number": "(074) 442-5701"},
        {"name": "Notre Dame de Chartres Hospital", "number": "(074) 619-8530"},
        {"name": "Baguio Medical Center (BMC)", "number": "(074) 442-3333"},
        {"name": "Pines City Doctors' Hospital", "number": "(074) 445-2PCD"}
    ],
    "fire": [
        {"name": "Baguio City Fire Department - Main", "number": "(074) 442-2222 or 911"},
        {"name": "Baguio City Fire Dept. (Market)", "number": "(074) 442-5211"},
        {"name": "Baguio City Fire Dept. (Aurora Hill)", "number": "(074) 442-7363"}
    ],
    "disaster_response": [
        {"name": "City Disaster Risk Reduction and Management Office (CDRRMO)", "number": "(074) 442-1900 or 911"},
        {"name": "Baguio-Benguet 911", "number": "911"}
    ]
}

@app.route('/')
def home():
    # A simple home page to show it's working
    return "Welcome to the Baguio City Emergency API. Go to /api/emergencynumbers to see the data."

@app.route('/api/emergencynumbers')
def get_emergency_numbers():
    return jsonify(emergency_data)

# --- IMPORTANT ---
# This code block makes it compatible with Render's deployment
if __name__ == "__main__":
    # Render uses the 'PORT' environment variable to assign a port.
    # We use 5000 as a default if running locally.
    port = int(os.environ.get('PORT', 5000))
    
    # '0.0.0.0' makes it listen on all available network interfaces,
    # which is required by Render.
    app.run(debug=False, host='0.0.0.0', port=port)
