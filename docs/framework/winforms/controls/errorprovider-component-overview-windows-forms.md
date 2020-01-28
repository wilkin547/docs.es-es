---
title: Información general del componente ErrorProvider
ms.date: 03/30/2017
f1_keywords:
- ErrorProvider
helpviewer_keywords:
- errors [Windows Forms], displaying to users
- error messages [Windows Forms], displaying
- ErrorProvider component [Windows Forms], about ErrorProvider component
ms.assetid: ced189f2-b5c8-46a7-a6f1-37f5af95dc99
ms.openlocfilehash: b66e97d97d0d8c2ea4e9bdba29f8ff35e486e1f6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745792"
---
# <a name="errorprovider-component-overview-windows-forms"></a>Información general del componente ErrorProvider (Formularios Windows Forms)
El componente Windows Forms [ErrorProvider](errorprovider-component-windows-forms.md) se usa para validar los datos proporcionados por el usuario en un formulario o control. Normalmente se utiliza junto con la validación de la entrada del usuario en un formulario o la visualización de errores dentro de un conjunto de datos. Un proveedor de errores es una alternativa mejor que mostrar un mensaje de error en un cuadro de mensaje, ya que una vez que se descarta un cuadro de mensaje, el mensaje de error ya no está visible. El componente <xref:System.Windows.Forms.ErrorProvider> muestra un icono de error (![un signo de exclamación en blanco dentro de un círculo rojo.](./media/errorprovider-component-overview-windows-forms/vb-error-provider-icon.gif)) junto al control correspondiente, como un cuadro de texto. Cuando el usuario coloca el puntero del mouse sobre el icono de error, aparece una información sobre herramientas que muestra la cadena del mensaje de error.  
  
## <a name="key-properties"></a>Propiedades clave  
 Las propiedades clave del componente <xref:System.Windows.Forms.ErrorProvider> son <xref:System.Windows.Forms.ErrorProvider.DataSource%2A>, <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A>y <xref:System.Windows.Forms.ErrorProvider.Icon%2A>. Al utilizar <xref:System.Windows.Forms.ErrorProvider> componente con controles enlazados a datos, la propiedad <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> se debe establecer en el contenedor adecuado (normalmente Windows Forms) para que el componente muestre un icono de error en el formulario. Cuando el componente se agrega en el diseñador, la propiedad <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> se establece en el formulario contenedor; Si agrega el control en el código, debe configurarlo.  
  
 La propiedad <xref:System.Windows.Forms.ErrorProvider.Icon%2A> se puede establecer en un icono de error personalizado en lugar del valor predeterminado. Cuando se establece la propiedad <xref:System.Windows.Forms.ErrorProvider.DataSource%2A>, el componente <xref:System.Windows.Forms.ErrorProvider> puede mostrar mensajes de error para un conjunto de DataSet. El método clave del componente <xref:System.Windows.Forms.ErrorProvider> es el <xref:System.Windows.Forms.ErrorProvider.SetError%2A> método, que especifica la cadena del mensaje de error y dónde debe aparecer el icono de error.  
  
> [!NOTE]
> El componente <xref:System.Windows.Forms.ErrorProvider> no proporciona compatibilidad integrada para los clientes de accesibilidad. Para que la aplicación sea accesible al usar este componente, debe proporcionar un mecanismo de comentarios adicional y accesible.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ErrorProvider>
- [Ver errores de un conjunto de datos con el componente ErrorProvider de formularios Windows Forms](view-errors-within-a-dataset-with-wf-errorprovider-component.md)
- [Mostrar iconos de error para la validación de formularios con el componente ErrorProvider de formularios Windows Forms](display-error-icons-for-form-validation-with-wf-errorprovider.md)
