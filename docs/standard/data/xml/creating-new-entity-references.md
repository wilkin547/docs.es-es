---
title: "Crear nuevas referencias de entidad | Microsoft Docs"
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
ms.assetid: a42f81b3-0403-4e34-b346-7d2129804e54
caps.latest.revision: 3
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# Crear nuevas referencias de entidad
El método **CreateEntityReference** crea un nuevo nodo **XmlEntityReference**.  El Modelo de objetos de documento \(DOM\) busca si el nombre de entidad al que se hace referencia ya se ha declarado.  Si es así, los nodos secundarios del nodo **XmlEntityReference** se copian desde el nodo de declaración de entidad.  Si no hay declaración de entidad equivalente, se adjunta un nodo de texto vacío como el único nodo secundario del nodo de referencia de entidad.  Puesto que los nodos secundarios de **XmlEntityReference** se copian de otros nodos, son de solo lectura y no pueden modificarse.  
  
 Al copiar los nodos, puede haber un espacio de nombres en el punto de la referencia de entidad.  Este espacio de nombres afecta la configuración de los elementos o nodos de atributo generados.  
  
> [!NOTE]
>  DOM agrega nodos secundarios a **EntityReference** solo cuando se inserta el nodo **EntityReference** en el documento.  Los nodos **EntityReference** recién creados no tienen nodos secundarios.  
  
 Aunque **XmlDataDocument** es una clase derivada de **XmlDocument**, **XmlDataDocument**no admite la creación de referencias de entidad.  Esto es debido a que los nodos secundarios de **EntityReference** son de solo lectura.  Los nodos secundarios de un nodo **EntityReference** pueden abarcar más de una región.  En este caso, parte de una fila asociada con la región que contiene parte de un nodo **EntityReference** será de solo lectura.  
  
## Vea también  
 [Modelo de objetos de documento XML \(DOM\)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)