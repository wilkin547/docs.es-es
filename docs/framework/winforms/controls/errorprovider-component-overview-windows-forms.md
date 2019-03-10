---
title: Información general del componente ErrorProvider (Formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ErrorProvider
helpviewer_keywords:
- errors [Windows Forms], displaying to users
- error messages [Windows Forms], displaying
- ErrorProvider component [Windows Forms], about ErrorProvider component
ms.assetid: ced189f2-b5c8-46a7-a6f1-37f5af95dc99
ms.openlocfilehash: 61a8d4baba35a7a8a8ae221b054029eb59107d0e
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57716262"
---
# <a name="errorprovider-component-overview-windows-forms"></a>Información general del componente ErrorProvider (Formularios Windows Forms)
Los formularios de Windows [ErrorProvider](errorprovider-component-windows-forms.md) componente se utiliza para validar la entrada del usuario en un formulario o control. Normalmente se utiliza junto con la validación de entrada del usuario en un formulario o mostrar errores dentro de un conjunto de datos. Un proveedor de errores es una alternativa mejor que mostrar un mensaje de error en un cuadro de mensaje, porque una vez que se cierra un cuadro de mensaje, el mensaje de error ya no está visible. El <xref:System.Windows.Forms.ErrorProvider> componente muestra un icono de error (![icono ErrorProvider](./media/vberrorprovidericon.gif "vbErrorProviderIcon")) junto al control correspondiente, por ejemplo, un cuadro de texto cuando el usuario coloca el puntero del mouse sobre el icono de error, que aparece una información sobre herramientas, que muestra la cadena de mensaje de error.  
  
## <a name="key-properties"></a>Propiedades clave  
 El <xref:System.Windows.Forms.ErrorProvider> son propiedades clave del componente <xref:System.Windows.Forms.ErrorProvider.DataSource%2A>, <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A>, y <xref:System.Windows.Forms.ErrorProvider.Icon%2A>. Cuando se usa <xref:System.Windows.Forms.ErrorProvider> componente con los controles enlazados a datos, el <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> propiedad debe establecerse en el contenedor adecuado (normalmente el formulario de Windows) para el componente mostrar un icono de error en el formulario. Cuando se agrega el componente en el diseñador, el <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> propiedad está establecida en el formulario contenedor; si agrega el control de código, debe establecer usted mismo.  
  
 El <xref:System.Windows.Forms.ErrorProvider.Icon%2A> propiedad puede establecerse en un icono de error personalizado en lugar del predeterminado. Cuando el <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> propiedad está establecida, el <xref:System.Windows.Forms.ErrorProvider> componente puede mostrar mensajes de error para un conjunto de datos. El método clave para el <xref:System.Windows.Forms.ErrorProvider> componente es el <xref:System.Windows.Forms.ErrorProvider.SetError%2A> método, que especifica la cadena de mensaje de error y dónde debe aparecer el icono de error.  
  
> [!NOTE]
>  El <xref:System.Windows.Forms.ErrorProvider> componente no proporciona compatibilidad integrada para los clientes de accesibilidad. Para que la aplicación sea accesible al utilizar este componente, debe proporcionar un mecanismo de comentarios adicionales y accesible.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.ErrorProvider>
- [Cómo: Ver errores de un conjunto de datos con el componente ErrorProvider de formularios Windows Forms](view-errors-within-a-dataset-with-wf-errorprovider-component.md)
- [Cómo: Mostrar iconos de Error de validación de formularios con el componente ErrorProvider de formularios Windows Forms](display-error-icons-for-form-validation-with-wf-errorprovider.md)
