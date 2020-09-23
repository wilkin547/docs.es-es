---
title: Cifrar y descifrar cadenas
ms.date: 07/20/2015
helpviewer_keywords:
- encryption [Visual Basic], strings
- strings [Visual Basic], encrypting
- decryption [Visual Basic], strings
- strings [Visual Basic], decrypting
ms.assetid: 1f51e40a-2f88-43e2-a83e-28a0b5c0d6fd
ms.openlocfilehash: e0e3fc332bf9430b1fa56dbb7630f849d3a29c2e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91072410"
---
# <a name="walkthrough-encrypting-and-decrypting-strings-in-visual-basic"></a>Tutorial: Cifrar y descifrar cadenas en Visual Basic

En este tutorial se muestra cómo usar la <xref:System.Security.Cryptography.DESCryptoServiceProvider> clase para cifrar y descifrar cadenas mediante la versión del proveedor de servicios criptográficos (CSP) del algoritmo Triple Data Encryption Standard ( <xref:System.Security.Cryptography.TripleDES> ). El primer paso consiste en crear una clase contenedora simple que encapsule el algoritmo 3DES y almacene los datos cifrados como una cadena codificada en base 64. A continuación, ese contenedor se usa para almacenar de forma segura los datos de usuario privados en un archivo de texto accesible públicamente.  
  
 Puede usar el cifrado para proteger los secretos del usuario (por ejemplo, contraseñas) y para que los usuarios no autorizados no puedan leer las credenciales. Esto puede impedir que la identidad de un usuario autorizado se robe, lo que protege los recursos del usuario y proporciona sin repudio. El cifrado también puede impedir que usuarios no autorizados tengan acceso a los datos de un usuario.  
  
 Para más información, vea [Servicios criptográficos](../../../../standard/security/cryptographic-services.md).  
  
> [!IMPORTANT]
> Los algoritmos de Rijndael (ahora denominados Estándar de cifrado avanzado [AES]) y del estándar de cifrado de datos triple (3DES) proporcionan una mayor seguridad que DES porque son más intensivo computacionalmente. Para obtener más información, vea <xref:System.Security.Cryptography.DES> y <xref:System.Security.Cryptography.Rijndael>.  
  
### <a name="to-create-the-encryption-wrapper"></a>Para crear el contenedor de cifrado  
  
1. Cree la `Simple3Des` clase para encapsular los métodos de cifrado y descifrado.  
  
     [!code-vb[VbVbalrStrings#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#38)]  
  
2. Agregue una importación del espacio de nombres Cryptography al inicio del archivo que contiene la `Simple3Des` clase.  
  
     [!code-vb[VbVbalrStrings#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#77)]  
  
3. En la `Simple3Des` clase, agregue un campo privado para almacenar el proveedor de servicios criptográficos de 3DES.  
  
     [!code-vb[VbVbalrStrings#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#39)]  
  
4. Agregue un método privado que cree una matriz de bytes de una longitud especificada a partir del hash de la clave especificada.  
  
     [!code-vb[VbVbalrStrings#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#41)]  
  
5. Agregue un constructor para inicializar el proveedor de servicios criptográficos de 3DES.  
  
     El `key` parámetro controla los `EncryptData` `DecryptData` métodos y.  
  
     [!code-vb[VbVbalrStrings#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#40)]  
  
6. Agregue un método público que cifre una cadena.  
  
     [!code-vb[VbVbalrStrings#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#42)]  
  
7. Agregue un método público que descifre una cadena.  
  
     [!code-vb[VbVbalrStrings#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#43)]  
  
     La clase contenedora ahora se puede usar para proteger los recursos de usuario. En este ejemplo, se usa para almacenar de forma segura los datos de usuario privados en un archivo de texto accesible públicamente.  
  
### <a name="to-test-the-encryption-wrapper"></a>Para probar el contenedor de cifrado  
  
1. En una clase independiente, agregue un método que use el método del contenedor `EncryptData` para cifrar una cadena y escribirla en la carpeta Mis documentos del usuario.  
  
     [!code-vb[VbVbalrStrings#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#78)]  
  
2. Agregue un método que lea la cadena cifrada de la carpeta Mis documentos del usuario y descifre la cadena con el método del contenedor `DecryptData` .  
  
     [!code-vb[VbVbalrStrings#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#79)]  
  
3. Agregue el código de la interfaz de usuario para llamar a los `TestEncoding` `TestDecoding` métodos y.  
  
4. Ejecute la aplicación.  
  
     Al probar la aplicación, tenga en cuenta que no descifrará los datos si proporciona una contraseña incorrecta.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Security.Cryptography>
- <xref:System.Security.Cryptography.DESCryptoServiceProvider>
- <xref:System.Security.Cryptography.DES>
- <xref:System.Security.Cryptography.TripleDES>
- <xref:System.Security.Cryptography.Rijndael>
- [servicios criptográficos](../../../../standard/security/cryptographic-services.md)
