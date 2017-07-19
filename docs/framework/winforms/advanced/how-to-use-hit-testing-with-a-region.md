---
title: "C&#243;mo: Utilizar la comprobaci&#243;n de visitas en una regi&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "prueba de visitas, con regiones"
  - "regiones, comprobación de visitas"
ms.assetid: 3a4c07cb-a40a-4d14-ad35-008f531910a8
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Utilizar la comprobaci&#243;n de visitas en una regi&#243;n
La comprobación de visitas tiene por objeto determinar si el cursor está situado encima de un determinado objeto, como un icono o un botón.  
  
## Ejemplo  
 En el siguiente ejemplo se crea una región con forma de signo más mediante la unión de dos regiones rectangulares.  Supongamos que la variable  `point`  almacena la ubicación del clic más reciente.  El código comprueba si  `point`  se encuentra en la región con forma de signo más.  Si dicha variable se encuentra en la región \(una visita\), la región se rellena con un pincel rojo opaco.  De lo contrario, la región se rellena con un pincel rojo semitransparente.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.MiscLegacyTopics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#31)]  
  
## Compilar el código  
 El ejemplo anterior está diseñado para formularios Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
## Vea también  
 <xref:System.Drawing.Region>   
 [Regiones de GDI\+](../../../../docs/framework/winforms/advanced/regions-in-gdi.md)   
 [Cómo: Utilizar el recorte en una región](../../../../docs/framework/winforms/advanced/how-to-use-clipping-with-a-region.md)