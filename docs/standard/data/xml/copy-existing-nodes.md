---
title: "Copiar nodos existentes | Microsoft Docs"
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
ms.assetid: 2aa8f65c-cc62-4638-9c46-129dc15be786
caps.latest.revision: 3
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# Copiar nodos existentes
Hay muchos métodos y propiedades en el Modelo de objetos del documento XML \(DOM\) que se pueden utilizar para seleccionar un nodo, como **SelectSingleNode**, **ChildNodes\[int i\]** o **Attributes\[int i\]**.  Una vez seleccionado el nodo, puede insertarlo en el árbol mediante uno de los métodos de inserción que funcionan para dicho tipo de nodo en particular.  La única restricción a la inserción de un nodo en el árbol es que el documento debe seguir teniendo un formato correcto después de insertarlo.  Al insertar un nodo existente en el árbol DOM, se quita de su posición original y se agrega a su posición de destino.  
  
## Vea también  
 [Modelo de objetos de documento XML \(DOM\)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)