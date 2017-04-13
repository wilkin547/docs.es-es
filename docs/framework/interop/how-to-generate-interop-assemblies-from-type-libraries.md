---
title: "How to: Generate Interop Assemblies from Type Libraries | Microsoft Docs"
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
  - "importing type library"
  - "interop assemblies, generating"
  - "Type Library Importer"
  - "type libraries"
  - "COM interop, importing type library"
ms.assetid: 4afd40c3-68f2-41c5-8ec1-4951bc148b9c
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# How to: Generate Interop Assemblies from Type Libraries
El [Importador de la biblioteca de tipos \(Tlbimp.exe\)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) es una herramienta de línea de comandos que convierte en metadatos las coclases y las interfaces contenidas en una biblioteca de tipos COM.  Esta herramienta crea de forma automática un ensamblado de interoperabilidad y un espacio de nombres para la información de tipos.  Una vez que los metadatos de una clase están disponibles, los clientes administrados pueden crear instancias del tipo COM y llamar a sus métodos, como si se tratase de una instancia de .NET.  Tlbimp.exe convierte en metadatos toda una biblioteca de tipos de una vez y no puede generar información de tipos para un subconjunto de los tipos definidos en una biblioteca de tipos.  
  
### Para generar un ensamblado de interoperabilidad a partir de una biblioteca de tipos  
  
1.  Utilice el comando siguiente:  
  
     **tlbimp** \<*archivo\_de\_biblioteca\_de\_tipos*\>  
  
     Si se agrega el modificador **\/out:** se genera un ensamblado de interoperabilidad con un nombre modificado, como LOANLib.dll.  La alteración del nombre del ensamblado de interoperabilidad ayuda a distinguirlo del DLL COM original y evita problemas que pueden surgir al tener nombres duplicados.  
  
## Ejemplo  
 El comando siguiente genera el ensamblado Loanlib.dll en el espacio de nombres `Loanlib`.  
  
```  
tlbimp Loanlib.dll  
```  
  
 El comando siguiente genera un ensamblado de interoperabilidad con un nombre modificado \(LOANLib.dll\).  
  
```  
tlbimp LoanLib.dll /out: LOANLib.dll  
```  
  
## Vea también  
 [Importing a Type Library as an Assembly](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)   
 [Exposing COM Components to the .NET Framework](../../../docs/framework/interop/exposing-com-components.md)