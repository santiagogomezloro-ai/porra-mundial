# ⚽ Porra Mundial 2026 – DXC Technology

> Aplicación de predicciones para el FIFA World Cup 2026, diseñada para empleados de DXC Technology.

---

## ¿Qué es?

La **Porra Mundial DXC 2026** es una aplicación web autocontenida (un único archivo HTML) que permite a los empleados de DXC realizar sus predicciones de resultados del Mundial de Fútbol 2026, que se celebrará del **11 de junio al 19 de julio de 2026** en Estados Unidos, México y Canadá.

Cada participante predice los marcadores de los 72 partidos de la fase de grupos, el avance de equipos a través del cuadro eliminatorio, el máximo goleador del torneo y el campeón. Al finalizar el torneo, el sistema calcula automáticamente la puntuación de cada persona y determina al ganador.

---

## ¿Para qué sirve?

- Fomentar el **compañerismo y la participación** entre empleados de DXC durante el Mundial.
- Ofrecer una **competición interna** basada en conocimiento futbolístico y algo de suerte.
- Centralizar todas las predicciones en una **base de datos administrada** por el organizador, que calcula los ganadores de forma objetiva y transparente.

---

## ¿Cómo funciona?

La aplicación tiene **dos roles** diferenciados: el participante y el administrador.

---

### Para los participantes

1. **Abrir el archivo** `index.html` en cualquier navegador (Chrome, Firefox, Safari, Edge). No requiere instalación ni registro.

2. **Introducir nombre y email** en la pantalla de bienvenida. El nombre identifica al participante de forma única en la base de datos.

3. **Rellenar las predicciones**, organizadas en dos fases:

   **Fase de grupos**
   - 12 grupos (A al L) con 4 equipos cada uno, siguiendo el sorteo oficial de la FIFA.
   - Para cada partido, se introduce el marcador predicho (goles equipo local – goles equipo visitante).
   - Debajo de cada grupo aparece una **clasificación provisional en tiempo real** que muestra cómo quedarían los equipos según los marcadores introducidos.

   **Fase eliminatoria**
   - Una vez rellenados los grupos, los **cruces de la Ronda de 32 se generan automáticamente** a partir de la clasificación predicha: el 1.º de cada grupo, el 2.º, y los 8 mejores terceros, emparejados según el calendario oficial de la FIFA.
   - A medida que se introducen resultados en dieciseisavos, el ganador de cada partido **pasa automáticamente** al siguiente cruce (octavos, cuartos, semifinales, final).
   - Si el marcador queda en empate, aparece un selector de **ganador por penaltis**.
   - El cuadro completo se construye así progresivamente, desde dieciseisavos hasta la gran final del 19 de julio.

   **Especiales**
   - Máximo goleador del torneo (nombre del jugador).
   - Campeón del Mundial (selección ganadora).

4. **Enviar predicciones** pulsando el botón correspondiente. Las predicciones quedan registradas en la base de datos. Se puede reenviar tantas veces como se quiera **hasta el 11 de junio de 2026** (inicio del torneo); cada reenvío sobreescribe la predicción anterior.

5. El botón **"Guardar borrador"** permite guardar localmente el progreso sin enviarlo, para continuar más tarde.

---

### Para el administrador

El acceso al panel de administrador se realiza desde la pantalla de bienvenida, haciendo clic en "Acceder al panel de admin" e introduciendo la contraseña.

El panel tiene tres secciones:

**Clasificación**
- Tabla con todos los participantes ordenados por puntuación.
- Muestra el número de partidos rellenados, marcadores exactos acertados, y si han acertado el goleador y el campeón.
- Botón para exportar la clasificación completa en formato CSV.
- Botón para refrescar los datos desde la base de datos en cualquier momento.

**Resultados**
- Formulario para introducir los marcadores reales de cada partido conforme se van jugando.
- Al guardar, la clasificación de todos los participantes se recalcula automáticamente.
- También permite registrar el goleador oficial y el campeón al término del torneo.

**Ver predicciones**
- Desplegable para consultar, partido a partido, la predicción de cualquier participante.
- Si ya hay resultados introducidos, muestra la puntuación obtenida en cada partido.

---

## Sistema de puntuación

| Predicción acertada | Puntos |
|---|---|
| Campeón del Mundial | +30 pts |
| Máximo goleador | +15 pts |
| Resultado exacto del partido | +3 pts |
| Goles del equipo local (sin acertar el total) | +1 pt |
| Goles del equipo visitante (sin acertar el total) | +1 pt |

La puntuación máxima por partido es de **5 puntos** (marcador exacto = 3 + 1 + 1). Los puntos son acumulativos: acertar el marcador exacto da 5 puntos, no 3.

Gana quien más puntos acumule al finalizar el torneo.

---

## Formato del torneo FIFA 2026

- **48 equipos** organizados en **12 grupos de 4**.
- Los **2 primeros de cada grupo** más los **8 mejores terceros** pasan a la fase eliminatoria (32 equipos en total).
- Ronda de 32 → Octavos de final → Cuartos de final → Semifinales → 3.º y 4.º puesto → **Gran Final** el 19 de julio en el MetLife Stadium (Nueva Jersey, EE.UU.).

---

## Estructura técnica

| Componente | Tecnología |
|---|---|
| Interfaz | HTML + CSS + JavaScript (sin frameworks, sin dependencias) |
| Almacenamiento local | `localStorage` del navegador (borrador) |
| Base de datos | Google Sheets (hoja de cálculo privada del administrador) |
| Backend | Google Apps Script (API gratuita, sin servidor) |
| Hosting | GitHub Pages (acceso web directo desde el repositorio) |

La aplicación no requiere ninguna instalación, servidor propio ni cuenta de pago. Todo funciona con herramientas gratuitas de Google y GitHub.

---

## Acceso web

La aplicación está disponible en:

**https://santiagogomezloro-ai.github.io/porra-mundial**

Puede compartirse este enlace directamente con los participantes. No es necesario descargar ningún archivo.

---

## Consideraciones importantes

- Las predicciones deben enviarse **antes del 11 de junio de 2026**, cuando arrancan los primeros partidos.
- El nombre introducido al registrarse identifica de forma única a cada participante. Si dos personas usan el mismo nombre, se sobreescribirán sus predicciones mutuamente.
- Los datos de los participantes (nombre, email y predicciones) se almacenan en la Google Sheets del organizador. Nadie más tiene acceso a esos datos.
- La contraseña del panel de administrador es **exclusiva para el organizador** y no debe compartirse con los participantes.

---

*Desarrollado para DXC Technology · Mundial FIFA 2026*
