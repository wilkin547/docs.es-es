---
title: Utilizar contenedores de gráficos
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], using containers
- graphics containers
- examples [Windows Forms], graphics containers
ms.assetid: 74632f91-cefa-4f51-ab7c-f9ac91942caf
ms.openlocfilehash: cfad7254057a31ea8268784cd4b6849850f3e2aa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766160"
---
# <a name="using-graphics-containers"></a>Utilizar contenedores de gráficos
Un <xref:System.Drawing.Graphics> objeto proporciona métodos como <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, y <xref:System.Drawing.Graphics.DrawString%2A> para mostrar imágenes vectoriales, imágenes de trama y texto. Un <xref:System.Drawing.Graphics> objeto también tiene varias propiedades que influyen en la calidad y la orientación de los elementos que se dibujan. Por ejemplo, la propiedad del modo suavizado determina si se aplica suavizado de contorno a líneas y curvas, y la propiedad de transformación del mundo influye en la posición y rotación de los elementos que se dibujan.  
  
 Un <xref:System.Drawing.Graphics> objeto está asociado con un dispositivo de presentación determinado. Cuando se usa un <xref:System.Drawing.Graphics> objeto que se va a dibujar en una ventana, el <xref:System.Drawing.Graphics> objeto también está asociado a esa ventana concreta.  
  
 Un <xref:System.Drawing.Graphics> objeto puede considerarse un contenedor porque contiene un conjunto de propiedades que afectan al dibujo y esté vinculado a información específica del dispositivo. Puede crear un contenedor secundario dentro de una existente <xref:System.Drawing.Graphics> objeto mediante una llamada a la <xref:System.Drawing.Graphics.BeginContainer%2A> método eso <xref:System.Drawing.Graphics> objeto.  
  
## <a name="in-this-section"></a>En esta sección  
 [Administrar el estado de un objeto Graphics](managing-the-state-of-a-graphics-object.md)  
 Describe cómo administrar la configuración de calidad, el área de recorte y transformaciones de un <xref:System.Drawing.Graphics> objeto.  
  
 [Utilizar contenedores de gráficos anidados](using-nested-graphics-containers.md)  
 Se muestra cómo utilizar los contenedores para controlar el estado de la <xref:System.Drawing.Graphics> objeto.
