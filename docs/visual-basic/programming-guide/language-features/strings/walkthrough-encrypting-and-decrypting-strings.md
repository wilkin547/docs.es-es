---
title: Cifrar y descifrar cadenas en Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- encryption [Visual Basic], strings
- strings [Visual Basic], encrypting
- decryption [Visual Basic], strings
- strings [Visual Basic], decrypting
ms.assetid: 1f51e40a-2f88-43e2-a83e-28a0b5c0d6fd
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fd9ec8e7af771db3f042e08c8ab30f6ed5832c2b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-encrypting-and-decrypting-strings-in-visual-basic"></a>Tutorial: Cifrar y descifrar cadenas en Visual Basic
En este tutorial se muestra cómo utilizar el <xref:System.Security.Cryptography.DESCryptoServiceProvider> clase para cifrar y descifrar cadenas utilizando la versión de servicios criptográficos (CSP) del proveedor de Triple Data Encryption Standard (<xref:System.Security.Cryptography.TripleDES>) algoritmo. El primer paso es crear una clase contenedora simple que encapsula el algoritmo 3DES y almacena los datos cifrados como una cadena codificada en base 64. A continuación, ese contenedor se utiliza para almacenar de forma segura los datos privados del usuario en un archivo de texto públicamente accesible.  
  
 Puede utilizar el cifrado para proteger los secretos del usuario (por ejemplo, contraseñas) y para hacer que las credenciales sean ilegibles por los usuarios no autorizados. Esto puede proteger la identidad de un usuario autorizado pueda ser sustraída, que protege los activos del usuario y proporciona sin repudio. Cifrado también puede proteger los datos de un usuario desde la que se va a obtener acceso a usuarios no autorizados.  
  
 Para obtener más información, consulte [servicios criptográficos](../../../../standard/security/cryptographic-services.md).  
  
> [!IMPORTANT]
>  Los algoritmos Triple Data Encryption Standard (3DES) y Rijndael (ahora conocido como estándar de cifrado avanzado [AES]) proporcionan una seguridad mayor que DES porque son más intensivo computacionalmente. Para obtener más información, consulte <xref:System.Security.Cryptography.DES> y <xref:System.Security.Cryptography.Rijndael>.  
  
### <a name="to-create-the-encryption-wrapper"></a>Para crear el contenedor de cifrado  
  
1.  Crear la `Simple3Des` clase para encapsular los métodos de cifrado y descifrado.  
  
     [!code-vb[VbVbalrStrings#38](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_1.vb)]  
  
2.  Agregue una importación del espacio de nombres de criptografía al principio del archivo que contiene el `Simple3Des` clase.  
  
     [!code-vb[VbVbalrStrings#77](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_2.vb)]  
  
3.  En el `Simple3Des` de la clase, agregue un campo privado para almacenar el proveedor de servicios criptográficos 3DES.  
  
     [!code-vb[VbVbalrStrings#39](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_3.vb)]  
  
4.  Agregue un método privado que crea una matriz de bytes de una longitud especificada del código hash de la clave especificada.  
  
     [!code-vb[VbVbalrStrings#41](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_4.vb)]  
  
5.  Agregue un constructor para inicializar el proveedor de servicios criptográficos 3DES.  
  
     El `key` parámetro controla la `EncryptData` y `DecryptData` métodos.  
  
     [!code-vb[VbVbalrStrings#40](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_5.vb)]  
  
6.  Agregue un método público que cifre una cadena.  
  
     [!code-vb[VbVbalrStrings#42](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_6.vb)]  
  
7.  Agregue un método público que se descifre una cadena.  
  
     [!code-vb[VbVbalrStrings#43](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_7.vb)]  
  
     La clase contenedora puede usarse ahora para proteger los activos de usuario. En este ejemplo, se usa para almacenar de forma segura los datos privados del usuario en un archivo de texto públicamente accesible.  
  
### <a name="to-test-the-encryption-wrapper"></a>Para probar el contenedor de cifrado  
  
1.  En una clase independiente, agregue un método que usa el contenedor `EncryptData` para cifrar una cadena y escribir al usuario de la carpeta Mis documentos.  
  
     [!code-vb[VbVbalrStrings#78](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_8.vb)]  
  
2.  Agregar un método que lee la cadena cifrada del usuario de la carpeta Mis documentos y descifra la cadena en el contenedor `DecryptData` método.  
  
     [!code-vb[VbVbalrStrings#79](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_9.vb)]  
  
3.  Agregar código de interfaz de usuario para llamar a la `TestEncoding` y `TestDecoding` métodos.  
  
4.  Ejecute la aplicación.  
  
     Al probar la aplicación, tenga en cuenta que no descifrará los datos si se proporciona una contraseña incorrecta.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Security.Cryptography>  
 <xref:System.Security.Cryptography.DESCryptoServiceProvider>  
 <xref:System.Security.Cryptography.DES>  
 <xref:System.Security.Cryptography.TripleDES>  
 <xref:System.Security.Cryptography.Rijndael>  
 [Servicios criptográficos](../../../../standard/security/cryptographic-services.md)
