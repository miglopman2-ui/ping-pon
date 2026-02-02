# 🏓 Juego de Ping Pong

## Descripción General

Este es un juego clásico de Ping Pong (Pong) implementado completamente en HTML5, CSS3 y JavaScript vanilla. El juego presenta una partida entre un jugador humano y la CPU, donde el objetivo es ser el primero en alcanzar 5 puntos.

## Características Principales

### Interfaz Visual
- **Diseño moderno**: Fondo degradado en tonos púrpura (#667eea a #764ba2)
- **Canvas estilizado**: Borde blanco redondeado con sombras para efecto de profundidad
- **Tablero de puntuación**: Muestra los puntos del jugador y la CPU en tiempo real
- **Pantalla de fin de juego**: Overlay que aparece cuando alguien gana la partida

### Mecánicas del Juego

#### Controles
- **Jugador**: Controla su paleta moviendo el mouse verticalmente
- La paleta del jugador sigue suavemente la posición del cursor

#### Elementos del Juego

**Pelota**
- Radio: 8 píxeles
- Velocidad inicial: 5 píxeles por frame en X e Y
- Velocidad máxima: 10 píxeles por frame
- Incrementa velocidad con cada rebote en las paletas (×1.05)
- Dirección inicial aleatoria al comenzar cada punto

**Paletas**
- Dimensiones: 12px de ancho × 80px de alto
- Paleta del jugador: Posición izquierda (x=20)
- Paleta de la CPU: Posición derecha (x=768)

#### Inteligencia Artificial de la CPU
La CPU tiene un sistema de IA básico pero efectivo:
- Sigue la posición vertical de la pelota
- Velocidad de movimiento: 4 píxeles por frame
- Zona muerta de ±35 píxeles para movimiento más natural
- Mantiene su paleta dentro de los límites del canvas

### Física del Juego

**Colisiones**
- Rebote en bordes superior e inferior del canvas
- Detección de colisión con ambas paletas
- Efecto de ángulo: La pelota cambia su dirección vertical según dónde impacte en la paleta

**Sistema de Puntuación**
- El jugador anota cuando la pelota sale por el lado derecho
- La CPU anota cuando la pelota sale por el lado izquierdo
- Primer jugador en llegar a 5 puntos gana
- Al anotar, la pelota se reinicia en el centro con dirección aleatoria

### Elementos Visuales del Canvas

- **Red central**: Línea punteada semi-transparente que divide el campo
- **Fondo**: Color gris oscuro (#2d3748)
- **Paletas y pelota**: Color blanco (#fff)
- **Cursor**: Oculto durante el juego para mejor experiencia

### Flujo del Juego

1. **Inicio**: El juego comienza automáticamente al cargar la página
2. **Jugando**: El loop del juego se ejecuta continuamente usando `requestAnimationFrame`
3. **Fin de partida**: Cuando un jugador alcanza 5 puntos
   - Se detiene el movimiento de la pelota
   - Aparece pantalla de game over con mensaje personalizado
   - Botón para reiniciar la partida

4. **Reinicio**: Al hacer clic en "Jugar de Nuevo"
   - Puntuaciones vuelven a 0
   - Pelota regresa al centro
   - El juego continúa

## Tecnologías Utilizadas

- **HTML5 Canvas**: Para renderizar los gráficos del juego
- **CSS3**: Estilos modernos con gradientes, sombras y efectos de blur
- **JavaScript Vanilla**: Lógica del juego sin dependencias externas

## Estructura del Código

### Objetos Principales
- `ball`: Posición, radio, velocidad y límites de la pelota
- `player`: Propiedades de la paleta del jugador
- `cpu`: Propiedades de la paleta de la CPU

### Funciones Principales
- `movePaddles()`: Actualiza posiciones de ambas paletas
- `moveBall()`: Actualiza posición de la pelota y detecta colisiones
- `draw()`: Renderiza todos los elementos en el canvas
- `gameLoop()`: Loop principal del juego
- `resetBall()`: Reinicia la pelota al centro
- `updateScore()`: Actualiza el marcador visual
- `endGame()`: Finaliza la partida y muestra ganador
- `resetGame()`: Reinicia todo el juego

## Experiencia de Usuario

El juego ofrece una experiencia fluida y responsive con:
- Animaciones suaves a 60 FPS (gracias a `requestAnimationFrame`)
- Feedback visual inmediato
- Interfaz intuitiva sin necesidad de instrucciones complejas
- Diseño atractivo y profesional

## Posibles Mejoras Futuras

- Niveles de dificultad ajustables
- Efectos de sonido
- Modo multijugador local
- Seguimiento de récords
- Efectos de partículas al anotar
- Modo oscuro/claro
