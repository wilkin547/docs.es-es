---
title: Punteros del mouse
ms.date: 03/30/2017
helpviewer_keywords:
- pointers [Windows Forms], setting
- mouse pointers
- mouse cursors
- mouse pointers [Windows Forms], setting
- cursors [Windows Forms], setting
- mouse [Windows Forms], cursors
ms.assetid: c3400d85-de5b-42e8-abc3-d6088d69ee53
ms.openlocfilehash: 4e8349effcd9b59045e39b763b4cb8b7d2fceb91
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740957"
---
# <a name="mouse-pointers-in-windows-forms"></a>Punteros del mouse (ratón) en formularios Windows Forms
El *puntero*del mouse, que a veces se conoce como cursor, es un mapa de bits que especifica un punto de enfoque en la pantalla para la entrada del usuario con el mouse. En este tema se proporciona información general sobre el puntero del mouse en Windows Forms y se describen algunas de las formas de modificar y controlar el puntero del mouse.  
  
## <a name="accessing-the-mouse-pointer"></a>Obtener acceso al puntero del mouse  
 El puntero del mouse se representa mediante la clase <xref:System.Windows.Forms.Cursor>, y cada <xref:System.Windows.Forms.Control> tiene una propiedad <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType> que especifica el puntero para ese control. La clase <xref:System.Windows.Forms.Cursor> contiene propiedades que describen el puntero, como las propiedades <xref:System.Windows.Forms.Cursor.Position%2A> y <xref:System.Windows.Forms.Cursor.HotSpot%2A>, y los métodos que pueden modificar la apariencia del puntero, como los métodos <xref:System.Windows.Forms.Cursor.Show%2A>, <xref:System.Windows.Forms.Cursor.Hide%2A>y <xref:System.Windows.Forms.Cursor.DrawStretched%2A>.  
  
## <a name="controlling-the-mouse-pointer"></a>Controlar el puntero del mouse  
 A veces, puede que desee limitar el área en la que se puede usar el puntero del mouse o cambiar la posición del mouse. Puede obtener o establecer la ubicación actual del mouse mediante la propiedad <xref:System.Windows.Forms.Cursor.Position%2A> de la <xref:System.Windows.Forms.Cursor>. Además, puede limitar el área en la que se puede usar el puntero del mouse para establecer la propiedad <xref:System.Windows.Forms.Cursor.Clip%2A>. De forma predeterminada, el área de recorte es toda la pantalla.  
  
## <a name="changing-the-mouse-pointer"></a>Cambiar el puntero del mouse  
 Cambiar el puntero del mouse es una forma importante de proporcionar comentarios al usuario. Por ejemplo, el puntero del mouse se puede modificar en los controladores de los eventos <xref:System.Windows.Forms.Control.MouseEnter> y <xref:System.Windows.Forms.Control.MouseLeave> para indicar al usuario que se están produciendo los cálculos y limitar la interacción del usuario en el control. A veces, el puntero del mouse cambiará debido a eventos del sistema, como cuando la aplicación está implicada en una operación de arrastrar y colocar.  
  
 La forma principal de cambiar el puntero del mouse es establecer la propiedad <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType> o <xref:System.Windows.Forms.Control.DefaultCursor%2A> de un control en una nueva <xref:System.Windows.Forms.Cursor>. Para obtener ejemplos de cómo cambiar el puntero del mouse, vea el ejemplo de código de la clase <xref:System.Windows.Forms.Cursor>. Además, la clase <xref:System.Windows.Forms.Cursors> expone un conjunto de objetos <xref:System.Windows.Forms.Cursor> para muchos tipos diferentes de punteros, como un puntero que se parece a una mano. Para mostrar el puntero de espera, que es similar a un reloj de arena, siempre que el puntero del mouse esté en el control, use la propiedad <xref:System.Windows.Forms.Control.UseWaitCursor%2A> de la clase <xref:System.Windows.Forms.Control>.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.Cursor>
- [Entradas mediante el mouse en una aplicación de Windows Forms](mouse-input-in-a-windows-forms-application.md)
- [Funcionalidad de arrastrar y soltar en Windows Forms](drag-and-drop-functionality-in-windows-forms.md)
