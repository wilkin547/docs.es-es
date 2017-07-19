---
title: "C&#243;mo: Comprobar la igualdad y la desigualdad de estructuras Test Point4D | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "igualdad, comprobar estructuras Point4D para"
  - "desigualdad, comprobar estructuras Point4D para"
  - "estructuras Point4D, comprobar la igualdad"
  - "estructuras Point4D, comprobar la desigualdad"
  - "pruebas, igualdad de estructuras Point4D"
  - "pruebas, desigualdad de estructuras Point4D"
ms.assetid: e004a67e-db7f-4af8-a31f-e6b2a44ccf34
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Comprobar la igualdad y la desigualdad de estructuras Test Point4D
En este ejemplo se muestra cómo probar la igualdad o desigualdad en las estructuras <xref:System.Windows.Media.Media3D.Point4D>.  
  
 En el código siguiente se muestra cómo probar la igualdad o desigualdad en las estructuras <xref:System.Windows.Media.Media3D.Point4D> utilizando los métodos de igualdad de <xref:System.Windows.Media.Media3D.Point4D>.  Se prueba la igualdad de las estructuras <xref:System.Windows.Media.Media3D.Point4D> mediante el operador sobrecargado `==` de igualdad; a continuación, se prueba su desigualdad mediante el operador sobrecargado `!=` de desigualdad; por último se comprueba la igualdad de una estructura <xref:System.Windows.Media.Media3D.Point3D> y una estructura <xref:System.Windows.Media.Media3D.Point4D> mediante el método estático <xref:System.Windows.Media.Media3D.Point4D.Equals%2A>.  
  
## Ejemplo  
 [!code-csharp[3DGallery_procedural_snip#Point4DEqualityExample_csharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Misc3DOperationsExample.cs#point4dequalityexample_csharp)]  
  
## Vea también  
 <xref:System.Windows.Media.Media3D.Point4D.op_Equality%2A>   
 <xref:System.Windows.Media.Media3D.Point4D.op_Inequality%2A>   
 <xref:System.Windows.Media.Media3D.Point4D.Equals%2A>