import streamlit as st
import matplotlib.pyplot as plt
from collections import Counter

# Page Configuration
st.set_page_config(page_title="Letter Frequency Graph", layout="centered")

st.title("📊 Name Letter Frequency Graph")

# Text Input
name = st.text_input("Name :", placeholder="Enter your name")

# Submit Button
if st.button("Submit"):

    if name.strip() == "":
        st.warning("Please enter a name.")
    else:
        # Remove spaces and convert to uppercase
        name = name.replace(" ", "").upper()

        # Count frequencies
        freq = Counter(name)

        letters = list(freq.keys())
        counts = list(freq.values())

        # Create Figure
        fig, ax = plt.subplots(figsize=(8, 5))

        bars = ax.bar(
            letters,
            counts,
            color="skyblue",
            edgecolor="black"
        )

        # Add values on top of bars
        for bar in bars:
            height = bar.get_height()
            ax.text(
                bar.get_x() + bar.get_width() / 2,
                height + 0.05,
                str(int(height)),
                ha="center",
                fontsize=12
            )

        ax.set_title("Letter Frequency")
        ax.set_xlabel("Letters")
        ax.set_ylabel("Frequency")

        st.subheader("Graph")
        st.pyplot(fig)
