---
title: "Cert2spc.exe (Software Publisher Certificate Test Tool) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "SPC"
  - "Software Publisher Certificate Test tool"
  - "Software Publisher Certificate"
  - "Cert2spc.exe"
  - "certificates, Software Publisher's Certificate"
ms.assetid: be434d7d-9c0d-46e7-8392-58a9b542d11d
caps.latest.revision: 21
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 21
---
# Cert2spc.exe (Software Publisher Certificate Test Tool)
La herramienta de prueba de certificados de editor de software crea un certificado de editor de software \(SPC\) a partir de uno o varios certificados X.509.  Cert2spc.exe se utiliza únicamente para pruebas.  Se puede obtener un certificado SPC válido de una entidad de certificación como VeriSign o Thawte.  Para obtener más información sobre cómo crear certificados X.509, vea [Makecert.exe \(Certificate Creation Tool\)](../Topic/Makecert.exe%20\(Certificate%20Creation%20Tool\).md).  
  
 Esta herramienta se instala automáticamente con Visual Studio.  Para ejecutar la herramienta, utilice el Símbolo del sistema para desarrolladores \(o el Símbolo del sistema de Visual Studio en Windows 7\).  Para obtener más información, vea [Símbolos del sistema](../../../docs/framework/tools/developer-command-prompt-for-vs.md).  
  
 En el símbolo del sistema, escriba lo siguiente:  
  
## Sintaxis  
  
```  
  
cert2spc cert1.cer | crl1.crl [... certN.cer | crlN.crl] outputSPCfile.spc  
```  
  
#### Parámetros  
  
|Argumento|Descripción|  
|---------------|-----------------|  
|`certN.cer`|Nombre de certificado X.509 que se incluye en el archivo SPC.  Se pueden especificar varios nombres separados por espacios.|  
|`crlN.crl`|Nombre de la lista de revocación de certificados que se va a incluir en el archivo SPC.  Se pueden especificar varios nombres separados por espacios.|  
|`outputSPCfile.spc`|Nombre del objeto PKCS \#7 que contendrá los certificados X.509.|  
  
|Opción|Descripción|  
|------------|-----------------|  
|**\/?**|Muestra las opciones y la sintaxis de los comandos para la herramienta.|  
  
## Ejemplos  
 El comando siguiente crea un SPC a partir de `myCertificate.cer` y lo coloca en `mySPCFile.spc`.  
  
```  
cert2spc myCertificate.cer mySPCFile.spc  
```  
  
 El comando siguiente crea un SPC a partir de `oneCertificate.cer` y `twoCertificate.cer` y lo coloca en `mySPCFile.spc`.  
  
```  
cert2spc oneCertificate.cer twoCertificate.cer mySPCFile.spc  
```  
  
## Vea también  
 [Tools](../../../docs/framework/tools/index.md)   
 [Makecert.exe \(Certificate Creation Tool\)](../Topic/Makecert.exe%20\(Certificate%20Creation%20Tool\).md)   
 [Símbolos del sistema](../../../docs/framework/tools/developer-command-prompt-for-vs.md)