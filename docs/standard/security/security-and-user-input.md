---
title: "Security and User Input | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "security [.NET Framework], user input"
  - "user input, security"
  - "secure coding, user input"
  - "code security, user input"
ms.assetid: 9141076a-96c9-4b01-93de-366bb1d858bc
caps.latest.revision: 7
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 5
---
# Security and User Input
Los datos proporcionados por el usuario, que pueden ser entradas de cualquier tipo \(datos de una solicitud Web o dirección URL, entrada de controles de una aplicación de formularios Microsoft Windows Forms, etc.\), pueden afectar negativamente al código, debido a que estos datos se suelen utilizar directamente como parámetros para llamar a otro código.  Ésta es una situación análoga a la que se produce cuando un código malintencionado llama a su código con parámetros desconocidos, por consiguiente, es necesario tomar las mismas precauciones.  En realidad, es más difícil conseguir que los datos que proporciona el usuario sean seguros ya que ningún marco de pila realiza el seguimiento de la posible existencia de datos que no sean de confianza.  
  
 Estos son los errores de seguridad más sutiles y que más cuesta localizar porque, aunque pueden existir en un código que aparentemente no guarde ninguna relación con la seguridad, son una puerta de enlace para pasar datos malintencionados a otro código.  Para buscar estos errores, siga cualquier tipo de dato introducido por el usuario, suponga un posible intervalo de valores y considere si su código puede controlar todos estos casos.  Puede solucionar estos errores mediante la comprobación y rechazo de cualquier entrada del intervalo que su código no pueda controlar.  
  
 Entre los aspectos que es importante considerar con relación a los datos de usuario están los siguientes:  
  
-   Todo dato de usuario en una respuesta de servidor se ejecuta en el contexto del sitio del servidor en el cliente.  Si el servidor web tiene datos de usuario y los inserta en la página Web devuelta, podría, por ejemplo, incluya una etiqueta de **\<script\>** y ejecute como si el servidor.  
  
-   Recuerde que el cliente puede solicitar cualquier dirección URL.  
  
-   Tenga en cuenta que las rutas de acceso siguientes son complicadas o no válidas:  
  
    -   .. \\, rutas de acceso extremadamente largas.  
  
    -   Rutas de acceso con caracteres comodín \(\*\).  
  
    -   Expansión con símbolo \(%token%\).  
  
    -   Formatos extraños de rutas de acceso con significados especiales.  
  
    -   Nombres alternativos en la secuencia del sistema de archivos, como `filename::$DATA`.  
  
    -   Versiones abreviadas de nombres de archivo, como `longfi~1` para `longfilename`.  
  
-   Recuerde que la expresión Eval\(userdata\) puede hacer cualquier cosa.  
  
-   Recele de los enlaces en tiempo de ejecución a nombres que incluyan algunos datos de usuario.  
  
-   En el tratamiento de datos de un sitio Web, tenga en cuenta las distintas secuencias de escape permitidas, entre las que se incluyen:  
  
    -   Secuencias de escape con codificación hexadecimal \(%nn\).  
  
    -   Secuencias de escape Unicode \(%nnn\).  
  
    -   Secuencias de escape UTF\-8 excesivamente largas \(%nn%nn\).  
  
    -   Secuencias de escape dobles \(%nn se convierte en %mmnn, donde %mm es la secuencia de escape para '%'\).  
  
-   Tenga en cuenta que los nombres de usuario pueden tener más de un formato canónico.  Por ejemplo, en Microsoft Windows 2000, con frecuencia se utiliza el formato MYDOMAIN\\*nombre de usuario* o el formato *nombredeusuario*@mydomain.example.com.  
  
## Vea también  
 [Secure Coding Guidelines](../../../docs/standard/security/secure-coding-guidelines.md)