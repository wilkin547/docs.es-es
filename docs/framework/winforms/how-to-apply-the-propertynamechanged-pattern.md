---
title: 'Cómo: Aplicar el modelo PropertyNameChanged'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property changes (using code)
- data binding [Windows Forms], custom controls
- PropertyNameChanged pattern [Windows Forms], applying
ms.assetid: aa47ddf6-5223-40c4-833f-a78992194836
ms.openlocfilehash: 775a27b1b4ba8143e297a3c4d323356a304073a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-apply-the-propertynamechanged-pattern"></a>Cómo: Aplicar el modelo PropertyNameChanged
En el ejemplo de código siguiente se muestra cómo aplicar el *PropertyName*modelo Changed a un control personalizado. Este patrón se aplican al implementar controles personalizados que se usan con el motor de enlace de datos de formularios Windows Forms.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.Windows.Forms.ChangeNotification#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/CS/Form1.cs#3)]
 [!code-vb[System.Windows.Forms.ChangeNotification#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para compilar el ejemplo de código anterior:  
  
-   Pegue el código en un archivo de código vacío. Debe utilizar el control personalizado en un formulario Windows Forms que contiene un `Main` método.  
  
## <a name="see-also"></a>Vea también  
 [Implementar la interfaz INotifyPropertyChanged](../../../docs/framework/winforms/how-to-implement-the-inotifypropertychanged-interface.md)  
 [Notificación de cambios en el enlace de datos de Windows Forms](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)  
 [Enlace de datos en Windows Forms](../../../docs/framework/winforms/windows-forms-data-binding.md)
