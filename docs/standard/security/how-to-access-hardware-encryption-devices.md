---
title: "How to: Access Hardware Encryption Devices | Microsoft Docs"
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
  - "encryption"
  - "key card"
  - "cryptography"
  - "hardware encryption"
  - "CspParameters"
ms.assetid: b0e734df-6eb4-4b16-b48c-6f0fe82d5f17
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# How to: Access Hardware Encryption Devices
Puede usar la clase <xref:System.Security.Cryptography.CspParameters> para obtener acceso a los dispositivos de cifrado de hardware.  Por ejemplo, puede usar esta clase para integrar la aplicación con una tarjeta inteligente, un generador de números aleatorios de hardware o una implementación de hardware de un determinado algoritmo criptográfico.  
  
 La clase <xref:System.Security.Cryptography.CspParameters> crea un proveedor de servicios criptográficos \(CSP\) que tiene acceso a un dispositivo de cifrado de hardware correctamente instalado.  Puede comprobar la disponibilidad de un CSP inspeccionando la siguiente clave del registro con el Editor del registro \(Regedit.exe\): HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Cryptography\\Defaults\\Provider.  
  
### Para firmar datos mediante una tarjeta de claves  
  
1.  Cree una instancia nueva de la clase <xref:System.Security.Cryptography.CspParameters>; para ello, pase el tipo de proveedor entero y el nombre del proveedor al constructor.  
  
2.  Pase las marcas adecuadas a la propiedad <xref:System.Security.Cryptography.CspParameters.Flags%2A> del objeto <xref:System.Security.Cryptography.CspParameters> recién creado.  Por ejemplo, pase la marca <xref:System.Security.Cryptography.CspProviderFlags>.  
  
3.  Cree una nueva instancia de una clase <xref:System.Security.Cryptography.AsymmetricAlgorithm> \(por ejemplo, la clase <xref:System.Security.Cryptography.RSACryptoServiceProvider>\) pasando el objeto <xref:System.Security.Cryptography.CspParameters> al constructor.  
  
4.  Firme los datos mediante uno de los métodos `Sign` y compruebe los datos mediante uno de los métodos `Verify`.  
  
### Para generar un número aleatorio mediante un generador de números aleatorios de hardware  
  
1.  Cree una instancia nueva de la clase <xref:System.Security.Cryptography.CspParameters>; para ello, pase el tipo de proveedor entero y el nombre del proveedor al constructor.  
  
2.  Cree una nueva instancia del <xref:System.Security.Cryptography.RNGCryptoServiceProvider> pasando el objeto <xref:System.Security.Cryptography.CspParameters> al constructor.  
  
3.  Cree un valor aleatorio con el método <xref:System.Security.Cryptography.RNGCryptoServiceProvider.GetBytes%2A> o <xref:System.Security.Cryptography.RNGCryptoServiceProvider.GetNonZeroBytes%2A>.  
  
## Ejemplo  
 En el siguiente ejemplo de código se muestra cómo firmar datos con una tarjeta inteligente.  El ejemplo de código crea un objeto <xref:System.Security.Cryptography.CspParameters> que expone una tarjeta inteligente e inicializa un objeto <xref:System.Security.Cryptography.RSACryptoServiceProvider> con el CSP.  Después, el ejemplo de código firma y comprueba algunos datos.  
  
 [!code-cpp[Cryptography.SmartCardCSP#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Cryptography.SmartCardCSP/CPP/Cryptography.SmartCardCSP.cpp#1)]
 [!code-csharp[Cryptography.SmartCardCSP#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Cryptography.SmartCardCSP/CS/example.cs#1)]
 [!code-vb[Cryptography.SmartCardCSP#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Cryptography.SmartCardCSP/VB/example.vb#1)]  
  
## Compilar el código  
  
-   Incluya los espacios de nombres <xref:System> y <xref:System.Security.Cryptography>.  
  
-   Debe tener un lector de tarjetas inteligentes y los controladores correspondientes instalados en el equipo.  
  
-   Debe inicializar el objeto <xref:System.Security.Cryptography.CspParameters> con la información específica de su lector de tarjetas.  Para obtener más información, consulte la documentación de su lector de tarjetas.