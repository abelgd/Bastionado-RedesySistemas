## Anexo — Revisión crítica y medidas adicionales de seguridad para el TP-Link Archer AX55

### Propósito

Este anexo complementa la guía principal con algunas observaciones sobre recomendaciones del fabricante y con medidas extra de bastionado que refuerzan la seguridad del Archer AX55.

La idea no es repetir lo ya explicado, sino señalar ciertos puntos que, aunque son cómodos para la configuración inicial, no siempre son los más adecuados desde un enfoque de seguridad.

### Observaciones críticas

#### Acceso por dominio frente a acceso por IP local

La documentación del AX55 permite acceder al panel mediante `tplinkwifi.net`, además de por la IP local. Aunque esto facilita el uso, para bastionar el equipo es preferible documentar y usar el acceso por IP local o por HTTPS interno, ya que así se evita depender de un dominio del fabricante.

**Conclusión práctica:** el acceso de administración debería realizarse preferentemente por IP local o por HTTPS, dejando el dominio como opción secundaria.

#### Red de invitados demasiado abierta en la documentación

Algunas guías públicas de TP-Link presentan la red de invitados con opciones que priorizan la comodidad, e incluso contemplan configuraciones poco restrictivas. Desde un punto de vista de seguridad, la red de invitados debe mantenerse siempre cifrada, con aislamiento entre clientes y sin acceso a la LAN principal.

**Conclusión práctica:** la red de invitados debe usarse solo con contraseña robusta y aislamiento activado, especialmente si se emplea para IoT o visitas.

#### Funciones VPN que no siempre conviene activar

El AX55 incorpora funciones de VPN Server y VPN Client, pero que estén disponibles no significa que deban activarse. Si no existe una necesidad real de acceso remoto, mantener estos servicios deshabilitados reduce superficie de ataque.

**Conclusión práctica:** la VPN solo debe habilitarse cuando haga falta y después de verificar firmware actualizado y configuración segura.

### Medidas adicionales propuestas

#### Revisar los cambios de firmware con más criterio

No basta con comprobar si hay una versión nueva. También conviene revisar qué corrige exactamente cada actualización, porque algunas versiones no solo parchean fallos, sino que también cambian comportamientos de seguridad.

#### Separar mejor la red principal de los dispositivos IoT

La red de invitados es útil, pero puede quedarse corta si se mezclan dispositivos de distinta confianza. Los equipos de trabajo, los personales y los IoT deberían separarse siempre que sea posible.

#### Reducir la dependencia del ecosistema del fabricante

Funciones como Tether o HomeShield pueden ser cómodas, pero también concentran más servicios y más dependencia del entorno de TP-Link. En una guía de bastionado conviene dejar claro qué servicios se usan realmente y cuáles pueden mantenerse desactivados.

### Valor del anexo

Este anexo aporta una lectura más crítica de la documentación oficial. La guía del fabricante está pensada para facilitar la instalación, mientras que el bastionado debe priorizar mínimo privilegio, reducción de superficie de ataque y desactivación de lo que no sea necesario.