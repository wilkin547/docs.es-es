---
title: "Tutorial: Cifrar y descifrar cadenas en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "descifrado, cadenas"
  - "cifrado, cadenas"
  - "cadenas [Visual Basic], descifrar"
  - "cadenas [Visual Basic], cifrar"
ms.assetid: 1f51e40a-2f88-43e2-a83e-28a0b5c0d6fd
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Tutorial: Cifrar y descifrar cadenas en Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Este tutorial muestra cómo utilizar la clase <xref:System.Security.Cryptography.DESCryptoServiceProvider> para cifrar y descifrar cadenas utilizando la versión del proveedor de servicios criptográficos \(CSP\) del algoritmo de Triple cifrado de datos estándar \(<xref:System.Security.Cryptography.TripleDES>\).  El primer paso consiste en crear una clase contenedora simple que encapsula el algoritmo \(3DES\) y almacena los datos cifrados como una cadena Base\-64 codificada.  A continuación, ese contenedor se utiliza para almacenar con seguridad los datos privados del usuario en un archivo de texto públicamente accesible.  
  
 Puede utilizar el cifrado para proteger secretos de usuario \(por ejemplo, contraseñas\) y hacer que las credenciales sean ilegibles por los usuarios no autorizados.  Así se puede proteger la identidad de un usuario autorizado contra su substracción, que protege los activos del usuario y proporciona su no repudiación.  El cifrado también puede proteger los datos de un usuario para que los usuarios no autorizados no puedan tener acceso a ellos.  
  
 Para obtener más información, vea [Servicios criptográficos](../Topic/Cryptographic%20Services.md).  
  
> [!IMPORTANT]
>  Los algoritmos Rijndael \(denominado en la actualidad como Estándar avanzado de cifrado \[AES\]\) y Triple cifrado de datos estándar \(3DES\) proporcionan una seguridad mayor que la de DES porque realizan una mayor carga computacional.  Para obtener más información, vea <xref:System.Security.Cryptography.DES> y <xref:System.Security.Cryptography.Rijndael>.  
  
### Para crear el contenedor de cifrado  
  
1.  Crear la clase `Simple3Des` para encapsular los métodos de cifrado y descifrado.  
  
     [!code-vb[VbVbalrStrings#38](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_1.vb)]  
  
2.  Agregue una importación de espacio de nombres de criptografía al principio del archivo que contiene la clase `Simple3Des` .  
  
     [!code-vb[VbVbalrStrings#77](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_2.vb)]  
  
3.  En la clase `Simple3Des` , agregue un campo privado para almacenar el proveedor de servicios criptográficos 3DES.  
  
     [!code-vb[VbVbalrStrings#39](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_3.vb)]  
  
4.  Agregar un método privado que cree una matriz de bytes de una longitud especificada a partir del hash de la clave especificada.  
  
     [!code-vb[VbVbalrStrings#41](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_4.vb)]  
  
5.  Agregar un constructor para inicializar el proveedor de servicios criptográficos 3DES.  
  
     El parámetro `key` controla los métodos `EncryptData` y `DecryptData`.  
  
     [!code-vb[VbVbalrStrings#40](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_5.vb)]  
  
6.  Agregue un método público que cifre una cadena.  
  
     [!code-vb[VbVbalrStrings#42](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_6.vb)]  
  
7.  Agregue un método público que descifre una cadena.  
  
     [!code-vb[VbVbalrStrings#43](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_7.vb)]  
  
     La clase contenedora se puede utilizar ahora para proteger los activos del usuario.  En este ejemplo, se utiliza para almacenar con seguridad los datos privados del usuario en un archivo de texto públicamente accesible.  
  
### Para probar el contenedor de cifrado  
  
1.  En una clase independiente, agregue un método que utilice el método `EncryptData` del contenedor para cifrar una cadena y escribirla en la carpeta Mis documentos del usuario.  
  
     [!code-vb[VbVbalrStrings#78](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_8.vb)]  
  
2.  Agregue un método que lea la cadena cifrada de la carpeta Mis documentos del usuario y descifre la cadena con el método `DecryptData` del contenedor.  
  
     [!code-vb[VbVbalrStrings#79](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_9.vb)]  
  
3.  Agregue el código de la interfaz de usuario para llamar a los métodos `TestEncoding` y `TestDecoding`.  
  
4.  Ejecute la aplicación.  
  
     Cuando pruebe la aplicación, fíjese en que no descifrará los datos si proporciona una contraseña incorrecta.  
  
## Vea también  
 <xref:System.Security.Cryptography>   
 <xref:System.Security.Cryptography.DESCryptoServiceProvider>   
 <xref:System.Security.Cryptography.DES>   
 <xref:System.Security.Cryptography.TripleDES>   
 <xref:System.Security.Cryptography.Rijndael>   
 [Servicios criptográficos](../Topic/Cryptographic%20Services.md)