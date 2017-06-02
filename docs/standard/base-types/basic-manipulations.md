---
title: "C&#243;mo: Realizar manipulaciones de cadena b&#225;sicas en .NET Framework | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "cadenas [.NET Framework], ejemplos"
ms.assetid: 121d1eae-251b-44c0-8818-57da04b8215e
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# C&#243;mo: Realizar manipulaciones de cadena b&#225;sicas en .NET Framework
En el ejemplo siguiente se utilizan algunos de los métodos descritos en los temas de [Operaciones básicas con cadenas](../../../docs/standard/base-types/basic-string-operations.md) para construir una clase que realiza manipulaciones de cadena de una manera que podría encontrarse en una aplicación real.  La clase `MailToData` guarda el nombre y la dirección de los individuos en propiedades distintas y proporciona un método para combinar los campos `City`, `State` y `Zip` en una única cadena para mostrársela al usuario.  Además, la clase permite al usuario escribir la información de la ciudad, el estado o provincia y el código postal como una única cadena. La aplicación analiza la cadena automáticamente e introduce la información adecuada en la propiedad correspondiente.  
  
 Para que resulte más sencillo, en este ejemplo se utiliza una aplicación de consola con una interfaz de línea de comandos.  
  
## Ejemplo  
 [!code-csharp[Conceptual.String.BasicOps#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/basicops.cs#1)]
 [!code-vb[Conceptual.String.BasicOps#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/basicops.vb#1)]  
  
 Cuando se ejecuta el código anterior, se pide al usuario que introduzca su nombre y dirección.  La aplicación coloca la información en las propiedades adecuadas y vuelve a mostrar la información al usuario, creando una única cadena que muestra la información de la ciudad, el estado o provincia y el código postal.  
  
## Vea también  
 [Operaciones básicas de cadenas](../../../docs/standard/base-types/basic-string-operations.md)