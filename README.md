import streamlit as st

st.title("Calcul de production et rendement")

production_theorique = st.number_input("Production théorique (kg)", min_value=0.0)
production_experimentale = st.number_input("Production expérimentale (kg)", min_value=0.0)

if production_theorique > 0:
    rendement = (production_experimentale / production_theorique) * 100
    perte = 100 - rendement
    st.write(f"**Rendement :** {rendement:.2f}%")
    st.write(f"**Perte :** {perte:.2f}%")
else:
    st.warning("Veuillez entrer une production théorique supérieure à 0.")
