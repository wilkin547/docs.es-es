---
title: Cifrar y descifrar cadenas en Visual Basic | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- encryption, strings
- strings [Visual Basic], encrypting
- decryption, strings
- strings [Visual Basic], decrypting
ms.assetid: 1f51e40a-2f88-43e2-a83e-28a0b5c0d6fd
caps.latest.revision: 18
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: ae3d599f7173162c07fbaeda60435615f101b10d
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-encrypting-and-decrypting-strings-in-visual-basic"></a>Tutorial: Cifrar y descifrar cadenas en Visual Basic
En este tutorial se muestra cómo utilizar el <xref:System.Security.Cryptography.DESCryptoServiceProvider>clase para cifrar y descifrar cadenas utilizando la versión de servicios criptográficos (CSP) del proveedor de Triple Data Encryption Standard (<xref:System.Security.Cryptography.TripleDES>) algoritmo.</xref:System.Security.Cryptography.TripleDES> </xref:System.Security.Cryptography.DESCryptoServiceProvider> El primer paso es crear una clase contenedora simple que encapsula el algoritmo 3DES y almacena los datos cifrados como una cadena codificada en base 64. A continuación, ese contenedor se utiliza para almacenar de forma segura los datos privados del usuario en un archivo de texto públicamente accesible.  
  
 Puede utilizar el cifrado para proteger secretos de usuario (por ejemplo, contraseñas) y hacer que las credenciales sean ilegibles por usuarios no autorizados. Esto puede proteger la identidad de un usuario autorizado contra su substracción, que protege los activos del usuario y proporciona el no repudio. Cifrado también puede proteger los datos de un usuario del acceso por usuarios no autorizados.  
  
 Para obtener más información, consulte [servicios criptográficos](http://msdn.microsoft.com/library/f96284bc-7b73-44b5-ac59-fac613ad09f8).  
  
> [!IMPORTANT]
>  Los algoritmos de Triple Data Encryption Standard (3DES) y Rijndael (conocido ahora como estándar de cifrado avanzado [AES]) proporcionan una seguridad mayor que DES porque son más intensivas. Para obtener más información, consulte <xref:System.Security.Cryptography.DES>y <xref:System.Security.Cryptography.Rijndael>.</xref:System.Security.Cryptography.Rijndael> </xref:System.Security.Cryptography.DES>  
  
### <a name="to-create-the-encryption-wrapper"></a>Para crear el contenedor de cifrado  
  
1.  Crear la `Simple3Des` clase para encapsular los métodos de cifrado y descifrado.  
  
     [!code-vb[VbVbalrStrings&#38;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_1.vb)]  
  
2.  Agregue una importación del espacio de nombres de criptografía al principio del archivo que contiene el `Simple3Des` clase.  
  
     [!code-vb[VbVbalrStrings&#77;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_2.vb)]  
  
3.  En el `Simple3Des` de clase, agregue un campo privado para almacenar el proveedor de servicios criptográficos 3DES.  
  
     [!code-vb[VbVbalrStrings&#39;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_3.vb)]  
  
4.  Agregue un método privado que se crea una matriz de bytes de una longitud especificada del hash de la clave especificada.  
  
     [!code-vb[VbVbalrStrings nº&41;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_4.vb)]  
  
5.  Agregue un constructor para inicializar el proveedor de servicios criptográficos 3DES.  
  
     El `key` parámetro controla la `EncryptData` y `DecryptData` métodos.  
  
     [!code-vb[VbVbalrStrings Nº&40;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_5.vb)]  
  
6.  Agregue un método público que cifre una cadena.  
  
     [!code-vb[VbVbalrStrings&#42;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_6.vb)]  
  
7.  Agregue un método público que descifre una cadena.  
  
     [!code-vb[VbVbalrStrings&#43;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_7.vb)]  
  
     Ahora se puede utilizar la clase contenedora para proteger los activos de usuario. En este ejemplo, sirve para almacenar de forma segura los datos privados del usuario en un archivo de texto públicamente accesible.  
  
### <a name="to-test-the-encryption-wrapper"></a>Para probar el contenedor de cifrado  
  
1.  En una clase independiente, agregue un método que usa el contenedor `EncryptData` método para cifrar una cadena y escribirla en el usuario de la carpeta Mis documentos.  
  
     [!code-vb[VbVbalrStrings&#78;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_8.vb)]  
  
2.  Agregue un método que lee la cadena cifrada del usuario de la carpeta Mis documentos y descifre la cadena con el contenedor `DecryptData` método.  
  
     [!code-vb[VbVbalrStrings&#79;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_9.vb)]  
  
3.  Agregue el código de la interfaz de usuario para llamar a la `TestEncoding` y `TestDecoding` métodos.  
  
4.  Ejecute la aplicación.  
  
     Cuando se prueba la aplicación, tenga en cuenta que no descifrará los datos si proporciona una contraseña incorrecta.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Security.Cryptography></xref:System.Security.Cryptography>   
 <xref:System.Security.Cryptography.DESCryptoServiceProvider></xref:System.Security.Cryptography.DESCryptoServiceProvider>   
 <xref:System.Security.Cryptography.DES></xref:System.Security.Cryptography.DES>   
 <xref:System.Security.Cryptography.TripleDES></xref:System.Security.Cryptography.TripleDES>   
 <xref:System.Security.Cryptography.Rijndael></xref:System.Security.Cryptography.Rijndael>   
 [Servicios criptográficos](http://msdn.microsoft.com/library/f96284bc-7b73-44b5-ac59-fac613ad09f8)
