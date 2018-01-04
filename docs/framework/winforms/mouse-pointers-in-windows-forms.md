---
title: "Punteros del mouse (ratón) en formularios Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pointers [Windows Forms], setting
- mouse pointers
- mouse cursors
- mouse pointers [Windows Forms], setting
- cursors [Windows Forms], setting
- mouse [Windows Forms], cursors
ms.assetid: c3400d85-de5b-42e8-abc3-d6088d69ee53
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: aaca18bff265fafbb5bad26adfe2a8c490d85132
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="mouse-pointers-in-windows-forms"></a>Punteros del mouse (ratón) en formularios Windows Forms
El mouse *puntero*, que a veces se conoce como el cursor es un mapa de bits que especifica un punto de enfoque en la pantalla para la entrada de usuario con el mouse. En este tema se proporciona información general del puntero del mouse (ratón) en formularios Windows Forms y describe algunas de las formas para modificar y controlar el puntero del mouse.  
  
## <a name="accessing-the-mouse-pointer"></a>Obtener acceso al puntero del Mouse  
 El puntero del mouse está representado por la <xref:System.Windows.Forms.Cursor> (clase) y cada <xref:System.Windows.Forms.Control> tiene un <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType> propiedad que especifica el puntero para ese control. El <xref:System.Windows.Forms.Cursor> clase contiene propiedades que describen el puntero, como la <xref:System.Windows.Forms.Cursor.Position%2A> y <xref:System.Windows.Forms.Cursor.HotSpot%2A> propiedades y métodos que pueden modificar la apariencia del puntero, como la <xref:System.Windows.Forms.Cursor.Show%2A>, <xref:System.Windows.Forms.Cursor.Hide%2A>, y <xref:System.Windows.Forms.Cursor.DrawStretched%2A> métodos.  
  
## <a name="controlling-the-mouse-pointer"></a>Controlar el puntero del Mouse  
 En ocasiones, puede que desee limitar el área en el que se puede utilizar el puntero del mouse o cambiar la posición del mouse. Puede obtener o establecer la ubicación actual del mouse (ratón) con el <xref:System.Windows.Forms.Cursor.Position%2A> propiedad de la <xref:System.Windows.Forms.Cursor>. Además, puede limitar el área que puede utilizarse el puntero del mouse puede configuración el <xref:System.Windows.Forms.Cursor.Clip%2A> propiedad. El área de recorte, de forma predeterminada, es la pantalla completa.  
  
## <a name="changing-the-mouse-pointer"></a>Cambiar el puntero del Mouse  
 Cambiar el puntero del mouse es un aspecto importante de proporcionar comentarios al usuario. Por ejemplo, el puntero del mouse puede modificarse en los controladores de la <xref:System.Windows.Forms.Control.MouseEnter> y <xref:System.Windows.Forms.Control.MouseLeave> para indicar al usuario que se están produciendo los cálculos y para limitar la interacción del usuario en el control de eventos. A veces, el puntero del mouse cambiará debido a eventos del sistema, como cuando la aplicación está implicada en una operación de arrastrar y colocar.  
  
 La manera principal para cambiar el puntero del mouse está definiendo el <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType> o <xref:System.Windows.Forms.Control.DefaultCursor%2A> propiedad de un control a una nueva <xref:System.Windows.Forms.Cursor>. Para obtener ejemplos de cambiar el puntero del mouse, vea el ejemplo de código en el <xref:System.Windows.Forms.Cursor> clase. Además, el <xref:System.Windows.Forms.Cursors> clase expone un conjunto de <xref:System.Windows.Forms.Cursor> objetos para muchos tipos distintos de punteros, como un puntero que se parece a una mano. Para mostrar el puntero de espera, que es similar a un reloj de arena, siempre que el puntero del mouse está sobre el control, use la <xref:System.Windows.Forms.Control.UseWaitCursor%2A> propiedad de la <xref:System.Windows.Forms.Control> clase.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.Cursor>  
 [Entradas mediante el mouse en una aplicación de Windows Forms](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)  
 [Funcionalidad de arrastrar y soltar en Windows Forms](../../../docs/framework/winforms/drag-and-drop-functionality-in-windows-forms.md)
