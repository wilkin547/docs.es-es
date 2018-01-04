---
title: "Utilizar contenedores de gráficos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [Windows Forms], using containers
- graphics containers
- examples [Windows Forms], graphics containers
ms.assetid: 74632f91-cefa-4f51-ab7c-f9ac91942caf
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 244f8e8a280369798daf12f8a61519826f937a4a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="using-graphics-containers"></a>Utilizar contenedores de gráficos
A <xref:System.Drawing.Graphics> objeto proporciona métodos como <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, y <xref:System.Drawing.Graphics.DrawString%2A> para mostrar imágenes vectoriales, imágenes de trama y texto. Un <xref:System.Drawing.Graphics> objeto también tiene varias propiedades que influyen en la calidad y la orientación de los elementos que se dibujan. Por ejemplo, la propiedad de modo de suavizado determina si se aplica el suavizado de contorno a líneas y curvas conectadas, y la propiedad de transformación universal influye en la posición y rotación de los elementos que se dibujan.  
  
 Un <xref:System.Drawing.Graphics> objeto está asociado a un determinado dispositivo de pantalla. Cuando se usa un <xref:System.Drawing.Graphics> objeto que se va a dibujar en una ventana, el <xref:System.Drawing.Graphics> objeto también está asociado a esa ventana concreta.  
  
 Un <xref:System.Drawing.Graphics> objeto puede considerarse un contenedor porque contiene un conjunto de propiedades que afectan al dibujo y se vincula a la información específica del dispositivo. Puede crear un contenedor secundario dentro de una existente <xref:System.Drawing.Graphics> objeto mediante una llamada a la <xref:System.Drawing.Graphics.BeginContainer%2A> método de dicha <xref:System.Drawing.Graphics> objeto.  
  
## <a name="in-this-section"></a>En esta sección  
 [Administrar el estado de un objeto Graphics](../../../../docs/framework/winforms/advanced/managing-the-state-of-a-graphics-object.md)  
 Describe cómo administrar la configuración de calidad, área de recorte y transformaciones de un <xref:System.Drawing.Graphics> objeto.  
  
 [Utilizar contenedores de gráficos anidados](../../../../docs/framework/winforms/advanced/using-nested-graphics-containers.md)  
 Muestra cómo utilizar los contenedores para controlar el estado de la <xref:System.Drawing.Graphics> objeto.
