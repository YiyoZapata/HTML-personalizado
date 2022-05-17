# HTML-personalizado

![Captura de pantalla de 2022-05-17 20-39-05](https://user-images.githubusercontent.com/100800688/168886378-121aa81f-46ee-4c93-b0bb-0f0b09064a95.png)


El localhost funciona, pero vamos a crear el nuestro propio que no sea nginx y lo paramos

![Captura de pantalla de 2022-05-17 13-58-55](https://user-images.githubusercontent.com/100800688/168887370-61b8df45-e22e-4fe0-8c99-a4262b96c9ac.png)

![Captura de pantalla de 2022-05-17 20-40-13](https://user-images.githubusercontent.com/100800688/168886793-09dfce93-f535-485a-a17e-53682ad1be86.png)

Crea un directorio en Documentos llamado nginx y dentro otro directorio llamado site-content. En este directorio, agrega un archivo index.html e introduce el siguiente html

![Captura de pantalla de 2022-05-17 14-09-43](https://user-images.githubusercontent.com/100800688/168887207-064c9edb-fb76-413e-8001-c30f044876b6.png)

![Captura de pantalla de 2022-05-17 20-53-19](https://user-images.githubusercontent.com/100800688/168888912-848e5281-9c4d-420f-bca2-98b33a3e45e4.png)

Crearun volumen para montar nuestro directorio local localmente en el contenedor de ejecución

![Captura de pantalla de 2022-05-17 20-55-43](https://user-images.githubusercontent.com/100800688/168889502-dbfcd193-cb98-47da-a28b-89a1cbbaf90e.png)

En el mismo directorio, crea un archivo llamado Dockerfile y pega los siguientes comandos.

FROM nginx:latest
COPY ./site-content/index.html /usr/share/nginx/html/index.html

![Captura de pantalla de 2022-05-17 15-53-04](https://user-images.githubusercontent.com/100800688/168890380-9dc220c2-b169-402b-8822-437e5170b2ec.png)

![Captura de pantalla de 2022-05-17 21-04-30](https://user-images.githubusercontent.com/100800688/168890699-0c61fdb1-4297-47fb-87c0-c4322f6ebef3.png)

Para construir nuestra imagen, ejecuta el siguiente comando:

![Captura de pantalla de 2022-05-17 21-07-48](https://user-images.githubusercontent.com/100800688/168891247-39407127-ffc8-45fa-b4e9-8a17e3e8c2a8.png)

Ahora podemos ejecutar nuestra imagen en un contenedor, pero esta vez no tenemos que crear un volumen para incluir nuestro html pues ya lo hacemos en el Dockerfile al copiar el archivo.

![Captura de pantalla de 2022-05-17 21-10-38](https://user-images.githubusercontent.com/100800688/168891665-7ff17fb3-cb3b-42ed-a1ce-2b5ae4161c48.png)

![Captura de pantalla de 2022-05-17 21-11-55](https://user-images.githubusercontent.com/100800688/168891859-688bbb18-996d-4f24-b264-1f540ec52147.png)


