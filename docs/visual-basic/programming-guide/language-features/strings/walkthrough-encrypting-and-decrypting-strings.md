---
title: Cifrar y descifrar cadenas en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- encryption [Visual Basic], strings
- strings [Visual Basic], encrypting
- decryption [Visual Basic], strings
- strings [Visual Basic], decrypting
ms.assetid: 1f51e40a-2f88-43e2-a83e-28a0b5c0d6fd
ms.openlocfilehash: fe91e0062ac35859a3b85eb080d16fb88a6f9aaf
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56972786"
---
# <a name="walkthrough-encrypting-and-decrypting-strings-in-visual-basic"></a>Tutorial: Cifrar y descifrar cadenas en Visual Basic
En este tutorial se muestra cómo usar el <xref:System.Security.Cryptography.DESCryptoServiceProvider> clase para cifrar y descifrar cadenas mediante la versión de servicios criptográficos (CSP) del proveedor de Triple Data Encryption Standard (<xref:System.Security.Cryptography.TripleDES>) algoritmo. El primer paso es crear una clase de contenedor simple que encapsula el algoritmo 3DES y almacena los datos cifrados como una cadena codificada en base 64. A continuación, ese contenedor se usa para almacenar de forma segura los datos privados del usuario en un archivo de texto accesible públicamente.  
  
 Puede utilizar cifrado para proteger los secretos de usuario (por ejemplo, contraseñas) y hacer que las credenciales no se puede leer los usuarios no autorizados. Esto puede proteger la identidad de un usuario autorizado desde que se lo roban, que protege los activos del usuario y proporciona el no rechazo. Cifrado también puede proteger datos de un usuario está accediendo a los usuarios no autorizados.  
  
 Para más información, vea [Servicios criptográficos](../../../../standard/security/cryptographic-services.md).  
  
> [!IMPORTANT]
>  Los algoritmos de Triple Data Encryption Standard (3DES) y Rijndael (conocido ahora como estándar de cifrado avanzado [AES]) proporcionan mayor seguridad que DES porque son más intensivas. Para obtener más información, vea <xref:System.Security.Cryptography.DES> y <xref:System.Security.Cryptography.Rijndael>.  
  
### <a name="to-create-the-encryption-wrapper"></a>Para crear el contenedor de cifrado  
  
1.  Crear el `Simple3Des` clase para encapsular los métodos de cifrado y descifrado.  
  
     [!code-vb[VbVbalrStrings#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#38)]  
  
2.  Agregue una importación del espacio de nombres de criptografía al principio del archivo que contiene el `Simple3Des` clase.  
  
     [!code-vb[VbVbalrStrings#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#77)]  
  
3.  En el `Simple3Des` clase, agregue un campo privado para almacenar el proveedor de servicios de cifrado 3DES.  
  
     [!code-vb[VbVbalrStrings#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#39)]  
  
4.  Agregue un método privado que crea una matriz de bytes de una longitud especificada del código hash de la clave especificada.  
  
     [!code-vb[VbVbalrStrings#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#41)]  
  
5.  Agregue un constructor para inicializar el proveedor de servicios de cifrado 3DES.  
  
     El `key` parámetro controla el `EncryptData` y `DecryptData` métodos.  
  
     [!code-vb[VbVbalrStrings#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#40)]  
  
6.  Agregue un método público que cifre una cadena.  
  
     [!code-vb[VbVbalrStrings#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#42)]  
  
7.  Agregue un método público que descifra una cadena.  
  
     [!code-vb[VbVbalrStrings#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#43)]  
  
     Ahora se puede usar la clase contenedora para proteger los activos de usuario. En este ejemplo, sirve para almacenar de forma segura los datos privados del usuario en un archivo de texto accesible públicamente.  
  
### <a name="to-test-the-encryption-wrapper"></a>Para probar el contenedor de cifrado  
  
1.  En una clase independiente, agregue un método que utiliza el contenedor `EncryptData` método para cifrar una cadena y escribirla en el usuario de la carpeta Mis documentos.  
  
     [!code-vb[VbVbalrStrings#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#78)]  
  
2.  Agregar un método que lee la cadena cifrada del usuario de la carpeta Mis documentos y descifra la cadena con el contenedor `DecryptData` método.  
  
     [!code-vb[VbVbalrStrings#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#79)]  
  
3.  Agregar código de interfaz de usuario para llamar a la `TestEncoding` y `TestDecoding` métodos.  
  
4.  Ejecute la aplicación.  
  
     Al probar la aplicación, tenga en cuenta que no descifrará los datos si se proporciona una contraseña incorrecta.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Security.Cryptography>
- <xref:System.Security.Cryptography.DESCryptoServiceProvider>
- <xref:System.Security.Cryptography.DES>
- <xref:System.Security.Cryptography.TripleDES>
- <xref:System.Security.Cryptography.Rijndael>
- [Cryptographic Services](../../../../standard/security/cryptographic-services.md)
