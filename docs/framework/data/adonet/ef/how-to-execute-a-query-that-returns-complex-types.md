---
title: "C&#243;mo: Ejecutar una consulta que devuelve tipos complejos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "ESQL"
  - "jsharp"
ms.assetid: c2209fdb-70ef-4dea-8bb8-097fe96f5563
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# C&#243;mo: Ejecutar una consulta que devuelve tipos complejos
En este tema se muestra cómo ejecutar una consulta [!INCLUDE[esql](../../../../../includes/esql-md.md)] que devuelve objetos de tipo entidad que contienen una propiedad de un tipo complejo.  
  
### Para ejecutar el código de este ejemplo  
  
1.  Agregue el [AdventureWorks Sales Model](http://msdn.microsoft.com/es-es/f16cd988-673f-4376-b034-129ca93c7832) al proyecto y configúrelo para usar [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  Para obtener más información, consulta [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/es-es/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
2.  En la página de código de la aplicación, agregue las instrucciones `using` siguientes \(`Imports` en Visual Basic\):  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3.  Haga doble clic en el archivo .edmx para mostrar el modelo en la [ventana del Explorador de modelos](http://msdn.microsoft.com/es-es/94e836e8-a5ea-47ff-aa3e-599d8a02ebfd) de Entity Designer.  En la superficie de Entity Designer, seleccione las propiedades `Email` y `Phone` del tipo de entidad `Contact` y, a continuación, haga clic con el botón secundario del mouse y seleccione **Refactorizar en un nuevo tipo complejo**.  
  
4.  Un nuevo tipo complejo con las propiedades `Email` y `Phone` seleccionadas se agrega al **Explorador de modelos**.  El tipo complejo recibe un nombre predeterminado: cambie el nombre del tipo a `EmailPhone` en la ventana **Propiedades**.  También se agrega una nueva propiedad `ComplexProperty` al tipo de entidad `Contact`.  Cambie el nombre de la propiedad a `EmailPhoneComplexType.`.  
  
     Para obtener información sobre cómo crear y modificar tipos complejos utilizando el Asistente para Entity Data Model, vea [How to: Refactor Existing Properties into a Complex Type Property](http://msdn.microsoft.com/es-es/5b2eb3b3-693d-42cb-b43a-405812d677eb) y [How to: Create and Modify Complex Types](http://msdn.microsoft.com/es-es/afb8e206-0ffe-4597-b6d4-6ab566897e1d).  
  
## Ejemplo  
 En el siguiente ejemplo se ejecuta una consulta que devuelve una colección de objetos `Contact` y muestra dos propiedades de los objetos `Contact` : `ContactID` y los valores del tipo complejo `EmailPhoneComplexType`.  
  
 [!code-csharp[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#complextypewithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#complextypewithentitycommand)]