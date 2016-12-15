---
title: "Instancias de objeto predeterminadas proporcionadas por My.Forms y My.WebServices (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Forms (objeto), desarrollar aplicaciones"
  - "My.WebServices (objeto), desarrollar aplicaciones"
  - "desarrollo rápido de aplicaciones (RAD), My.Forms"
  - "desarrollo rápido de aplicaciones (RAD), My.WebServices"
ms.assetid: de930027-9108-4f0c-b97c-5e7db4d6ef79
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Instancias de objeto predeterminadas proporcionadas por My.Forms y My.WebServices (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Los objetos [My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md) y [My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md) proporcionan acceso a formularios, orígenes de datos y servicios Web XML utilizados por la aplicación.  Para ello, proporcionan colecciones de *instancias predeterminadas* de cada uno de estos objetos.  
  
## Instancias predeterminadas  
 Una instancia predeterminada es una instancia de la clase proporcionada por el tiempo de ejecución que no necesita declararse ni crearse como instancia con las instrucciones `Dim` y `New`.  En el ejemplo siguiente se muestra cómo se ha podido declarar y crear la instancia de una clase llamada <xref:System.Windows.Forms.Form> `Form1`, y cómo ahora puede obtener una instancia predeterminada de esta clase <xref:System.Windows.Forms.Form> mediante `My.Forms`.  
  
 [!code-vb[VbVbcnMy#5](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/default-object-instances-provided-by-my-forms-and-my-webservices_1.vb)]  
  
 [!code-vb[VbVbcnMy#6](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/default-object-instances-provided-by-my-forms-and-my-webservices_2.vb)]  
  
 El objeto `My.Forms` devuelve una colección de instancias predeterminadas para cada clase `Form` que existe en su proyecto.  De igual forma, `My.WebServices` proporciona una instancia predeterminada de la clase de proxy para cada servicio Web al que ha creado una referencia en su aplicación.  
  
## Vea también  
 [My.Forms \(Objeto\)](../../../visual-basic/language-reference/objects/my-forms-object.md)   
 [My.WebServices \(Objeto\)](../../../visual-basic/language-reference/objects/my-webservices-object.md)   
 [Cómo My depende del tipo de proyecto](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)