## Arquitectura del Servicio de Notificaciones

El **Servicio de Notificaciones** actúa como un consumidor de eventos generados por otros servicios del sistema. Su única responsabilidad actual es la gestión y envío de **correos electrónicos**; no se implementarán notificaciones push ni otros formatos en esta etapa.

---

### 🟢 Gestión de Cuentas y Seguridad

Estos correos garantizan la integridad de los perfiles de usuario y la seguridad de sus credenciales.

* **Verificación de Correo Electrónico:** * Se envía al crear una cuenta nueva.
* *Nota:* Aunque el usuario puede navegar por la aplicación sin verificar su correo, tendrá acceso limitado (por ejemplo, no podrá crear una cuenta de vendedor ni contactar a otros usuarios).

* **Restablecimiento de Contraseña:**
* **Solicitud:** Instrucciones enviadas cuando un usuario olvida su clave.
* **Confirmación:** Notificación de seguridad enviada una vez que el cambio de contraseña se ha realizado con éxito.

---

### 🤝 Comunicación y Ofertas

Correos activados por la interacción directa entre compradores y vendedores.

* **Ofertas Personalizadas:** * Se envía al comprador cuando un vendedor emite una "oferta personalizada" o un "gig a medida" tras una negociación (por ejemplo, un ajuste de precio de $20 a $15).

---

### 📦 Gestión de Pedidos (Workflow de Órdenes)

El servicio gestiona cinco tipos específicos de correos relacionados con el ciclo de vida de un pedido:

1. **Colocación de Pedido:** Notificación al vendedor informándole que un comprador ha adquirido uno de sus servicios.
2. **Recibo de Pago:** Comprobante enviado al comprador tras confirmar que el pago se ha procesado correctamente.
3. **Solicitud de Extensión de Tiempo:** Enviada por el vendedor al comprador cuando requiere más tiempo para completar la entrega.
4. **Aprobación o Rechazo de Extensión:** Notificación al vendedor con la decisión final del comprador sobre la solicitud de tiempo adicional.
5. **Entrega de Pedido:** Aviso al comprador de que el vendedor ha entregado el trabajo finalizado.

---

### 📌 Notas Adicionales

Para fines de este curso, nos limitaremos a los correos mencionados anteriormente. No obstante, el sistema es escalable y permite añadir nuevas notificaciones en el futuro, tales como:

* Alertas de nuevas reseñas (de comprador o vendedor).
* Actualizaciones de estado adicionales.
