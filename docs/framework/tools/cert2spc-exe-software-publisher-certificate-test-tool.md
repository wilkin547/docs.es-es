---
title: Cert2spc.exe (Herramienta de prueba de certificados del publicador de software)
description: Use Cert2spc.exe, la herramienta de prueba de certificados del publicador de software. Esta herramienta crea un certificado de publicador de software (SPC) a partir de uno o varios certificados X.509.
ms.date: 03/30/2017
helpviewer_keywords:
- SPC
- Software Publisher Certificate Test tool
- Software Publisher Certificate
- Cert2spc.exe
- certificates, Software Publisher's Certificate
ms.assetid: be434d7d-9c0d-46e7-8392-58a9b542d11d
ms.openlocfilehash: 0bcc785a51f2ca46195970130178d0cfa705ee6e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96247328"
---
# <a name="cert2spcexe-software-publisher-certificate-test-tool"></a>Cert2spc.exe (Herramienta de prueba de certificados del publicador de software)

La herramienta de prueba de certificados de editor de software crea un certificado de editor de software (SPC) a partir de uno o varios certificados X.509. Cert2spc.exe se utiliza únicamente para pruebas. Se puede obtener un certificado SPC válido de una entidad de certificación como VeriSign o Thawte. Para más información sobre cómo crear certificados X.509, consulte [Makecert.exe (Herramienta de creación de certificados)](/windows/desktop/SecCrypto/makecert).  
  
 Esta herramienta se instala automáticamente con Visual Studio. Para ejecutar la herramienta, use Símbolo del sistema para desarrolladores de Visual Studio (o Símbolo del sistema de Visual Studio en Windows 7). Para más información, consulte [Símbolos del sistema](developer-command-prompt-for-vs.md).  
  
 En el símbolo del sistema, escriba lo siguiente:  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
cert2spc cert1.cer | crl1.crl [... certN.cer | crlN.crl] outputSPCfile.spc  
```  
  
## <a name="parameters"></a>Parámetros  
  
|Argumento|Descripción|  
|--------------|-----------------|  
|`certN.cer`|Nombre de certificado X.509 que se incluye en el archivo SPC. Se pueden especificar varios nombres separados por espacios.|  
|`crlN.crl`|Nombre de la lista de revocación de certificados que se va a incluir en el archivo SPC. Se pueden especificar varios nombres separados por espacios.|  
|`outputSPCfile.spc`|Nombre del objeto PKCS #7 que contendrá los certificados X.509.|  
  
|Opción|Descripción|  
|------------|-----------------|  
|**/?**|Muestra las opciones y la sintaxis de los comandos para la herramienta.|  
  
## <a name="examples"></a>Ejemplos  

 El comando siguiente crea un SPC a partir de `myCertificate.cer` y lo coloca en `mySPCFile.spc`.  
  
```console
cert2spc myCertificate.cer mySPCFile.spc  
```  
  
 El comando siguiente crea un SPC a partir de `oneCertificate.cer` y `twoCertificate.cer` y lo coloca en `mySPCFile.spc`.  
  
```console
cert2spc oneCertificate.cer twoCertificate.cer mySPCFile.spc  
```  
  
## <a name="see-also"></a>Vea también

- [Herramientas](index.md)
- [Makecert.exe (Herramienta de creación de certificados)](/windows/desktop/SecCrypto/makecert)
- [Símbolos del sistema](developer-command-prompt-for-vs.md)
