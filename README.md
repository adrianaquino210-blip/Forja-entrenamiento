# FORJA — tu app de entrenamiento gratis

FORJA es una primera versión funcional, con diseño oscuro moderno, inspirada en la categoría de apps de entrenamiento. No copia marca, código ni recursos propietarios de Gymtone.

## Funciones disponibles
- Inicio con resumen semanal.
- Cuatro rutinas editables de fuerza/hipertrofia.
- Registro de peso y repeticiones por serie.
- Temporizador de descanso de 90 segundos.
- Historial y gráfico de volumen registrado.
- Perfil físico.
- Exportación e importación de una copia JSON.
- Modo local funcional sin cuenta.
- Inicio de sesión y sincronización con Supabase una vez configurado.

## Para probarla ya
Abrí `index.html` en un navegador moderno. En modo archivo, la app funciona localmente; las funciones de sincronización requieren alojarla en una dirección HTTPS.

## Sincronización gratuita entre dispositivos
1. Creá un proyecto en https://supabase.com (plan gratuito sujeto a límites del proveedor).
2. En Supabase, abrí **SQL Editor**, pegá todo el contenido de `schema.sql` y ejecutalo.
3. En **Project Settings > API** (o sección equivalente), copiá el Project URL y la clave `anon`/`publishable` pública.
4. Pegalos en `config.js` en `url` y `anonKey`. No uses nunca la clave `service_role`.
5. En Authentication, configurá el proveedor Email. Para probar con facilidad podés desactivar confirmación de email, aunque para uso real es preferible mantenerla activada.
6. Publicá la carpeta en un hosting estático HTTPS gratuito, por ejemplo GitHub Pages, Cloudflare Pages o Netlify. No hace falta comprar créditos para el hosting básico, pero cada proveedor puede cambiar sus límites y condiciones.
7. Abrí la URL desde el iPhone y desde el otro dispositivo. Registrate con la misma cuenta en ambos. Usá “Sincronizar ahora” después de entrenar.

## Instalar en iPhone
1. Abrí la web publicada en Safari.
2. Tocá Compartir.
3. Elegí **Agregar a pantalla de inicio**.
4. Abrila desde el nuevo ícono.

## Seguridad
- El archivo `schema.sql` activa Row Level Security (RLS) y limita el acceso a la fila del usuario autenticado.
- La clave `anon`/public del frontend no es secreta; la seguridad depende de RLS y las políticas.
- Nunca pegues una clave `service_role` en `config.js`.
- Si usás una contraseña, no la reutilices de otros servicios.

## Importante sobre la primera versión
- Esta versión es un prototipo funcional inicial, no una copia exacta de Gymtone.
- El modo local guarda datos en el navegador del dispositivo. Si borrás los datos del navegador, se pueden perder; exportá copias regularmente.
- Al sincronizar por primera vez entre dispositivos, elegí un dispositivo como principal y hacé una copia JSON antes de combinar datos. La sincronización inicial usa la fecha más reciente de las sesiones como criterio sencillo.
- La app no reemplaza la orientación de un profesional. Adaptá las cargas a tu experiencia, técnica, lesiones y recuperación. Frená si sentís dolor agudo, mareo o malestar.
