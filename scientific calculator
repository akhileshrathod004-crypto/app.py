import streamlit as st
import math

st.set_page_config(page_title="Glitch Scientific Calculator", page_icon="🧮", layout="centered")

# -------- CUSTOM CSS FOR BLACK BACKGROUND + GLITCH POPUP -------- #
glitch_css = """
<style>

body {
    background-color: black !important;
}

[data-testid="stAppViewContainer"] {
    background-color: black !important;
}

/* Popup box */
.glitch-box {
    width: 90%;
    padding: 20px;
    margin: 20px auto;
    text-align: center;
    font-size: 24px;
    font-weight: bold;
    background: rgba(0, 10, 30, 0.7);
    border: 2px solid #1a3cff;
    border-radius: 10px;
    color: #4da3ff;
    animation: glitch 1s infinite;
}

/* Glitch animation */
@keyframes glitch {
    0% { text-shadow: 2px 2px #001eff; }
    20% { text-shadow: -2px -2px #0036ff; }
    40% { text-shadow: 3px -3px #0051ff; }
    60% { text-shadow: -3px 3px #0019ff; }
    80% { text-shadow: 2px -2px #002cff; }
    100% { text-shadow: 0px 0px #001eff; }
}

</style>
"""
st.markdown(glitch_css, unsafe_allow_html=True)

# -------- GLITCH POPUP -------- #
st.markdown(
    '<div class="glitch-box">SYSTEM ALERT: Scientific Calculator Activated</div>',
    unsafe_allow_html=True
)

# -------- CALCULATOR APP -------- #
st.title("🧮 Scientific Calculator")

# User input
num1 = st.number_input("Enter first number", value=0.0)
num2 = st.number_input("Enter second number (for binary ops)", value=0.0)

operation = st.selectbox("Select an operation", [
    "Add", "Subtract", "Multiply", "Divide",
    "Power", "Square Root", "Sin", "Cos", "Tan", "Log"
])

if st.button("Calculate"):
    try:
        if operation == "Add":
            result = num1 + num2
        elif operation == "Subtract":
            result = num1 - num2
        elif operation == "Multiply":
            result = num1 * num2
        elif operation == "Divide":
            result = "Error: Cannot divide by zero" if num2 == 0 else num1 / num2
        elif operation == "Power":
            result = math.pow(num1, num2)
        elif operation == "Square Root":
            result = "Error: Negative number" if num1 < 0 else math.sqrt(num1)
        elif operation == "Sin":
            result = math.sin(math.radians(num1))
        elif operation == "Cos":
            result = math.cos(math.radians(num1))
        elif operation == "Tan":
            result = math.tan(math.radians(num1))
        elif operation == "Log":
            result = "Error: Non-positive number" if num1 <= 0 else math.log10(num1)

        st.success(f"Result: {result}")
    except Exception as e:
        st.error(f"Calculation error: {e}")
