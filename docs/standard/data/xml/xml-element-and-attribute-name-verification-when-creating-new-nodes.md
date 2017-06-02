---
title: "Comprobaci&#243;n de nombres de atributos y elementos XML al crear nodos nuevos | Microsoft Docs"
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
ms.assetid: b489f647-a175-4659-ada4-170058bb41d0
caps.latest.revision: 5
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 5
---
# Comprobaci&#243;n de nombres de atributos y elementos XML al crear nodos nuevos
El modelo de objetos de documento \(DOM\) XML comprueba la validez de los nombres cuando se crean nuevos nodos de elementos o de atributos.  Si los nombres contienen caracteres no válidos, se produce una excepción.  Para asegurarse de que los nombres son válidos y que están codificados correctamente, deberá usar la clase **XmlConvert** para codificar el nombre y decodificarlo de nuevo en el nivel de aplicación.  El **XmlWriter** cuenta con métodos que realizan trabajo adicional para asegurar que se genera XML con el formato correcto.  
  
## Vea también  
 [Modelo de objetos de documento XML \(DOM\)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)