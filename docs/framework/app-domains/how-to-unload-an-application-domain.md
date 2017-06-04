---
title: "C&#243;mo: Descargar un dominio de aplicaci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Unload (método)"
  - "dominios de aplicación, descargar"
  - "descargar dominios de aplicación"
ms.assetid: f356116d-e415-4f7c-a332-6e6a60227192
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Descargar un dominio de aplicaci&#243;n
Cuando se termina de utilizar un dominio de aplicación, se descarga con el método [System.AppDomain.Unload](frlrfSystemAppDomainClassUnloadTopic).  El método **Unload** cierra discretamente el dominio de aplicación especificado.  Durante el proceso de descarga, ningún subproceso nuevo puede obtener acceso al dominio de aplicación mientras se liberan todas las estructuras de datos específicas del dominio de la aplicación.  
  
 Los ensamblados cargados en el dominio de aplicación se quitan y dejan de estar disponibles.  Si un ensamblado del dominio de aplicación es neutral respecto al dominio, sus datos permanecen en la memoria hasta que se cierra todo el proceso.  No existe ningún mecanismo para descargar un ensamblado neutral con respecto al dominio, aparte de cerrar todo el proceso.  Hay situaciones en las que la solicitud de descargar un dominio de aplicación no funciona y genera una <xref:System.CannotUnloadAppDomainException>.  
  
 En el ejemplo siguiente se crea un nuevo dominio de aplicación denominado `MyDomain`, se imprime cierta información en la consola y, a continuación, se descarga el dominio de aplicación.  Tenga en cuenta que, después, el código intenta imprimir en la consola el nombre descriptivo del dominio de aplicación descargado.  Esta acción genera una excepción que controlan las instrucciones Try\/Catch que se encuentran al final del programa.  
  
## Ejemplo  
 [!code-cpp[System.AppDomain.Load#3](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.appdomain.load/cpp/source3.cpp#3)]
 [!code-csharp[System.AppDomain.Load#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.load/cs/source3.cs#3)]
 [!code-vb[System.AppDomain.Load#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.load/vb/source3.vb#3)]  
  
## Vea también  
 [Programming with Application Domains](http://msdn.microsoft.com/es-es/bd36055b-56bd-43eb-b4d8-820c37172131)   
 [Cómo: Crear un dominio de aplicación](../../../docs/framework/app-domains/how-to-create-an-application-domain.md)   
 [Utilizar dominios de aplicación](../../../docs/framework/app-domains/use.md)