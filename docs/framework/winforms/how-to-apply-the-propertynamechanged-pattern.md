---
title: Procedimiento para aplicar el patrón PropertyNameChanged
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property changes (using code)
- data binding [Windows Forms], custom controls
- PropertyNameChanged pattern [Windows Forms], applying
ms.assetid: aa47ddf6-5223-40c4-833f-a78992194836
ms.openlocfilehash: 01afa713e97206ea192ba55dc2affad20163f872
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665261"
---
# <a name="how-to-apply-the-propertynamechanged-pattern"></a>Procedimiento para aplicar el patrón PropertyNameChanged
En el ejemplo de código siguiente se muestra cómo aplicar el *PropertyName*patrón ha cambiado a un control personalizado. Este patrón se aplican al implementar controles personalizados que se usan con el motor de enlace de datos de Windows Forms.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.Windows.Forms.ChangeNotification#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/CS/Form1.cs#3)]
 [!code-vb[System.Windows.Forms.ChangeNotification#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para compilar el ejemplo de código anterior:  
  
- Pegue el código en un archivo de código vacío. Debe usar el control personalizado en un formulario de Windows que contenga un `Main` método.  
  
## <a name="see-also"></a>Vea también

- [Cómo: Implementar la interfaz INotifyPropertyChanged](how-to-implement-the-inotifypropertychanged-interface.md)
- [Notificación de cambios en el enlace de datos de Windows Forms](change-notification-in-windows-forms-data-binding.md)
- [Enlace de datos en Windows Forms](windows-forms-data-binding.md)
