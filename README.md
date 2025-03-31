# 🧮 Calculadora de Propinas - Readme

Una aplicación interactiva para calcular propinas y dividir el total entre comensales de manera justa y sencilla.

## 🌟 Características

- 💵 Cálculo automático de propinas basado en porcentaje
- 👥 División del total entre múltiples personas
- 🎚 Interfaz con controles deslizantes intuitivos
- 💫 Animaciones y diseño visual atractivo
- 📱 Diseño responsive que se adapta a diferentes dispositivos

## 🛠 Tecnologías Utilizadas

- **HTML5** - Estructura semántica de la aplicación
- **CSS3** - Estilos y animaciones
- **JavaScript** - Lógica y manipulación del DOM
- **Gradientes CSS** - Para el diseño visual atractivo
- **Transiciones y Animaciones CSS** - Para mejorar la experiencia de usuario

## 🚀 Funcionamiento

La aplicación permite a los usuarios:

1. Ingresar el monto total de la cuenta
2. Seleccionar el porcentaje de propina deseado (1%-100%)
3. Especificar el número de personas que compartirán la cuenta
4. Visualizar automáticamente:
   - Propina total
   - Monto total a pagar (cuenta + propina)
   - Propina por persona
   - Total por persona

### 💻 Código Destacado

#### Manipulación del DOM

```javascript
const sliders = document.querySelectorAll("input[type='range']");
sliders.forEach(function(slider){
    slider.addEventListener("input", calculateTip)
});

const billInput = document.getElementById("bill");
billInput.addEventListener("change",calculateTip);
```

Este fragmento:

- Selecciona todos los controles deslizantes (range inputs)

- Añade event listeners para ejecutar la función `calculateTip` cuando cambian

- También detecta cambios en el input del monto de la cuenta

### Función Principal de Cálculo

```javascript
function calculateTip() {
    let bill = parseFloat(billInput.value);
    let tipPercent = document.getElementById("tip").value;
    let noOfPeople = document.getElementById("no-of-people").value;

    billInput.value = bill.toFixed(2);

    let totalTip = parseFloat((bill * (tipPercent/100)).toFixed(2));
    let total = parseFloat((bill + totalTip).toFixed(2));

    let tipPerPerson = (totalTip/noOfPeople).toFixed(2);
    let totalPerPerson = (total/noOfPeople).toFixed(2);

    // Actualización de los elementos del DOM
    document.getElementById("tip-amount").textContent = `$${totalTip}`;
    // ... más actualizaciones ...
}
```

Esta función:

1. Obtiene los valores de entrada (monto, porcentaje de propina, número de personas)

1. Realiza los cálculos matemáticos necesarios

1. Actualiza todos los elementos visuales con los nuevos resultados

## 🎨 Diseño y Animaciones
La aplicación cuenta con efectos visuales atractivos:

```css
@keyframes slideIn {
    from { top: -50%; }
    to { top: 50%; }
}

@keyframes fadeIn {
    from { opacity: 0; }
    to { opacity: 1; }
}
```

- **slideIn**: Animación de entrada del contenedor principal

- **fadeIn**: Efecto de aparición gradual para la sección de resultados

- **Transiciones suaves** para cambios de color y estado

## 📥 Instalación y Uso
### Para usuarios finales:

1. Clona el repositorio:

```bash
git clone https://github.com/Seb-RM/Javascript_Html_Css-Tip-Calculator.git
```

2. Abre el proyecto en tu editor de código favorito

1. Abre el archivo `index.html` en tu navegador web favorito

1. ¡Listo! La aplicación está lista para usar

3. Personaliza según tus necesidades

## 🕹 Cómo Usar la Aplicación
1. **Ingresa el monto total** de la cuenta en el campo "Bill"

1. **Ajusta el porcentaje de propina** usando el deslizador (o escribe directamente)

1. **Selecciona el número de personas** que compartirán la cuenta

1. **Observa los resultados** que se actualizan en tiempo real:

    - Propina total

    - Total a pagar (cuenta + propina)

    - Monto por persona

## 🏆 Conceptos Aplicados
- **Manipulación del DOM**: Selección y actualización dinámica de elementos

- **Event Listeners**: Detección de cambios en controles de entrada

- **Cálculos matemáticos**: Operaciones con porcentajes y divisiones

- **Formateo de números**: Mostrar valores monetarios con 2 decimales

- **Animaciones CSS**: Mejora de la experiencia de usuario
