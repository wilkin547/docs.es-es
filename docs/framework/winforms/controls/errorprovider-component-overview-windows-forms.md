---
title: "Información general del componente ErrorProvider (Formularios Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ErrorProvider
helpviewer_keywords:
- errors [Windows Forms], displaying to users
- error messages [Windows Forms], displaying
- ErrorProvider component [Windows Forms], about ErrorProvider component
ms.assetid: ced189f2-b5c8-46a7-a6f1-37f5af95dc99
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8b47e55461610d2cc4bf85c839ddb1bef937d69e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="errorprovider-component-overview-windows-forms"></a>Información general del componente ErrorProvider (Formularios Windows Forms)
Los formularios Windows Forms [ErrorProvider](../../../../docs/framework/winforms/controls/errorprovider-component-windows-forms.md) componente se utiliza para validar datos proporcionados por el usuario en un formulario o control. Normalmente se utiliza junto con la validación proporcionados por el usuario en un formulario o mostrar los errores dentro de un conjunto de datos. Un proveedor de errores es una alternativa mejor que mostrar un mensaje de error en un cuadro de mensaje, porque una vez que se cierra un cuadro de mensaje, el mensaje de error ya no está visible. El <xref:System.Windows.Forms.ErrorProvider> componente muestra un icono de error (![icono ErrorProvider](../../../../docs/framework/winforms/controls/media/vberrorprovidericon.gif "vbErrorProviderIcon")) junto al control correspondiente, por ejemplo, un cuadro de texto; cuando el usuario coloca el puntero del mouse sobre el icono de error, que aparece una información sobre herramientas, que muestra la cadena de mensaje de error.  
  
## <a name="key-properties"></a>Propiedades clave  
 El <xref:System.Windows.Forms.ErrorProvider> las propiedades clave del componente son <xref:System.Windows.Forms.ErrorProvider.DataSource%2A>, <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A>, y <xref:System.Windows.Forms.ErrorProvider.Icon%2A>. Cuando se usa <xref:System.Windows.Forms.ErrorProvider> componente con controles enlazados a datos, la <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> propiedad debe establecerse en el contenedor adecuado (habitualmente el formulario Windows Forms) en orden para el componente mostrar un icono de error en el formulario. Cuando se agrega el componente en el diseñador, el <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> propiedad se establece en el formulario contenedor; si agrega el control en el código, debe establecerlo de usted mismo.  
  
 El <xref:System.Windows.Forms.ErrorProvider.Icon%2A> propiedad puede establecerse en un icono de error personalizado en lugar del predeterminado. Cuando el <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> propiedad está establecida, la <xref:System.Windows.Forms.ErrorProvider> componente puede mostrar los mensajes de error para un conjunto de datos. El método clave de la <xref:System.Windows.Forms.ErrorProvider> componente es el <xref:System.Windows.Forms.ErrorProvider.SetError%2A> método, que especifica la cadena de mensaje de error y dónde debe aparecer el icono de error.  
  
> [!NOTE]
>  El <xref:System.Windows.Forms.ErrorProvider> componente no proporciona compatibilidad integrada para los clientes de accesibilidad. Para que la aplicación sea accesible al utilizar este componente, debe proporcionar un mecanismo de retroalimentación adicional accesible.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.ErrorProvider>  
 [Ver errores de un conjunto de datos con el componente ErrorProvider de formularios Windows Forms](../../../../docs/framework/winforms/controls/view-errors-within-a-dataset-with-wf-errorprovider-component.md)  
 [Mostrar iconos de error para la validación de formularios con el componente ErrorProvider de formularios Windows Forms](../../../../docs/framework/winforms/controls/display-error-icons-for-form-validation-with-wf-errorprovider.md)
