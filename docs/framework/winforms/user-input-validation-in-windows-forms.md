---
title: "Validación de los datos proporcionados por el usuario en formularios Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, validating user input
- validation [Windows Forms], Windows Forms user input
- user input [Windows Forms], validating in Windows Forms
- validating user input [Windows Forms], Windows Forms
ms.assetid: 4ec07681-1dee-4bf9-be5e-718f635a33a1
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1eba92d764e73360b1cd58957ea5318c5b263b8b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="user-input-validation-in-windows-forms"></a>Validación de los datos proporcionados por el usuario en formularios Windows Forms
Cuando los usuarios escriben datos en la aplicación, puede que desee comprobar que los datos son válidos antes de que la aplicación usa. Puede requerir que determinados campos de texto no sea de longitud cero, que tenga formato de un campo como un número de teléfono u otro tipo de datos con formato correcto o que una cadena no contiene ningún carácter no seguro que podría usarse para poner en peligro la seguridad de una base de datos. Windows Forms proporciona varias maneras de validar los datos introducidos en la aplicación.  
  
## <a name="validation-with-the-maskedtextbox-control"></a>Validación con el Control MaskedTextBox  
 Si tiene que requieren los usuarios escriban datos en un formato bien definido, como un número de teléfono o un número de pieza, puede hacerlo rápidamente y con un mínimo de código mediante el uso de la <xref:System.Windows.Forms.MaskedTextBox> control. A *máscara* es una cadena formada por caracteres de un lenguaje de enmascaramiento que especifica qué caracteres se pueden especificar en cualquier posición dada en el cuadro de texto. El control muestra un conjunto de mensajes al usuario. Si el usuario escribe una entrada incorrecta, por ejemplo, el usuario escribe una letra cuando se requiere un dígito, el control rechazará automáticamente la entrada.  
  
 El lenguaje de enmascaramiento que se usa por <xref:System.Windows.Forms.MaskedTextBox> es muy flexible. Permite especificar caracteres necesarios, caracteres opcionales, los caracteres literales, como guiones y paréntesis, caracteres de divisa y separadores de fecha. El control también funciona bien cuando se enlaza a un origen de datos. El <xref:System.Windows.Forms.Binding.Format> evento en un enlace de datos puede utilizarse para cambiar el formato de los datos entrantes para cumplir con la máscara y el <xref:System.Windows.Forms.Binding.Parse> evento puede utilizarse para cambiar el formato de los datos salientes para cumplir con las especificaciones del campo de datos.  
  
 Para obtener más información, consulte [MaskedTextBox (Control)](../../../docs/framework/winforms/controls/maskedtextbox-control-windows-forms.md).  
  
## <a name="event-driven-validation"></a>Validación orientada a eventos  
 Si desea un control completo mediante programación sobre validación o que deba realizar comprobaciones de validación complejo, debe utilizar los eventos de validación integrados en la mayoría de los controles de formularios Windows Forms. Cada control que acepta datos proporcionados por el usuario de forma libre tiene un <xref:System.Windows.Forms.Control.Validating> eventos que se producirán cada vez que el control requiere una validación de datos. En el <xref:System.Windows.Forms.Control.Validating> método de control de eventos, puede validar entrada de varias maneras de usuario. Por ejemplo, si tiene un cuadro de texto que debe contener un código postal, puede realizar la validación de las maneras siguientes:  
  
-   Si el código postal debe pertenecer a un grupo específico de códigos postales, puede realizar una comparación de cadenas en la entrada para validar los datos introducidos por el usuario. Por ejemplo, si el código postal debe estar en el conjunto {10001, 10002, 10003}, puede usar una comparación de cadenas para validar los datos.  
  
-   Si el código postal debe estar en un formulario específico puede usar expresiones regulares para validar los datos introducidos por el usuario. Por ejemplo, para validar el formato `#####` o `#####-####`, puede utilizar la expresión regular `^(\d{5})(-\d{4})?$`. Para validar el formulario `A#A #A#`, puede utilizar la expresión regular `[A-Z]\d[A-Z] \d[A-Z]\d`. Para obtener más información sobre las expresiones regulares, vea [expresiones regulares de .NET Framework](../../../docs/standard/base-types/regular-expressions.md) y [ejemplos de expresiones regulares](../../../docs/standard/base-types/regular-expression-examples.md).  
  
-   Si el código postal debe ser un código postal de Estados Unidos válido, podría llamar a un servicio Web de código postal para validar los datos introducidos por el usuario.  
  
 El <xref:System.Windows.Forms.Control.Validating> eventos se proporciona un objeto de tipo <xref:System.ComponentModel.CancelEventArgs>. Si decide que los datos del control no sean válidos, puede cancelar la <xref:System.Windows.Forms.Control.Validating> eventos mediante el establecimiento de este objeto <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> propiedad `true`. Si no establece la <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> propiedad, formularios Windows Forms se supone que la validación se realizó correctamente para ese control y genera el <xref:System.Windows.Forms.Control.Validated> eventos.  
  
 Para obtener un ejemplo de código que valida una dirección de correo electrónico en un <xref:System.Windows.Controls.TextBox>, consulte <xref:System.Windows.Forms.Control.Validating>.  
  
### <a name="data-binding-and-event-driven-validation"></a>Enlace de datos y validación orientada a eventos  
 Validación resulta muy útil cuando se debe enlazar los controles a un origen de datos, como una tabla de base de datos. Mediante la validación, puede asegurarse de que los datos del control satisfacen el formato requerido por el origen de datos, y que no contienen caracteres especiales, como las comillas y realizar copias de las barras diagonales podrían no ser seguro.  
  
 Cuando se usa el enlace de datos, los datos en el control se sincronizan con el origen de datos durante la ejecución de la <xref:System.Windows.Forms.Control.Validating> eventos. Si se cancela el <xref:System.Windows.Forms.Control.Validating> eventos, los datos no se sincronizarán con el origen de datos.  
  
> [!IMPORTANT]
>  Si tiene una validación personalizada que tiene lugar después de la <xref:System.Windows.Forms.Control.Validating> eventos, no se verán afectadas el enlace de datos. Por ejemplo, si tiene código en un <xref:System.Windows.Forms.Control.Validated> eventos que intenta cancelar el enlace de datos, el enlace de datos se llevarán a cabo. En este caso, para realizar la validación en el <xref:System.Windows.Forms.Control.Validated> eventos, cambie el control **modo de actualización del origen de datos** propiedad (**bajo (Databindings)**\\**(avanzado)** ) desde **OnValidation** a **nunca**y agregue *Control*`.DataBindings["`*\<YOURFIELD >*  `"].WriteValue()` para el código de validación.  
  
### <a name="implicit-and-explicit-validation"></a>Validación implícita y explícita  
 ¿Por lo que si de un control validan los datos? Esto depende de usted, el desarrollador. Puede utilizar la validación implícita o explícita, según las necesidades de la aplicación.  
  
#### <a name="implicit-validation"></a>Validación implícita  
 El enfoque de validación implícita valida los datos cuando el usuario escribe en él. Puede validar los datos como los datos se escribe en un control leyendo las teclas que se presionan, o incluso más habitualmente siempre que el usuario tiene el foco de entrada fuera de un control y se desplaza a la siguiente. Este enfoque es útil cuando desea proporcionar al usuario información inmediata acerca de los datos tal y como están funcionando.  
  
 Si desea utilizar la validación implícita para un control, debe establecer ese control <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> propiedad `true`. Si cancela la <xref:System.Windows.Forms.Control.Validating> eventos, el comportamiento del control vendrá determinado por el valor que se ha asignado a <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A>. Si asignó <xref:System.Windows.Forms.AutoValidate.EnablePreventFocusChange>, al cancelar el evento hará que el <xref:System.Windows.Forms.Control.Validated> no que se produzca evento. Foco de entrada permanecerá en el control actual hasta que el usuario cambia los datos a una entrada válida. Si asignó <xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>, el <xref:System.Windows.Forms.Control.Validated> evento no se producirá cuando cancele el evento, pero el foco todavía cambiará al siguiente control.  
  
 Asignar <xref:System.Windows.Forms.AutoValidate.Disable> a la <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> propiedad evita la validación implícita por completo. Para validar los controles, tendrá que utilizar la validación explícita.  
  
#### <a name="explicit-validation"></a>Validación explícita  
 El enfoque de validación explícita valida los datos al mismo tiempo. Puede validar los datos en respuesta a una acción del usuario, como hacer clic en un botón Guardar o un vínculo siguiente. Cuando se produce la acción del usuario, puede desencadenar la validación explícita en una de las maneras siguientes:  
  
-   Llame a <xref:System.Windows.Forms.ContainerControl.Validate%2A> para validar el último control que ha perdido el foco.  
  
-   Llame a <xref:System.Windows.Forms.ContainerControl.ValidateChildren%2A> para validar todos los controles secundarios en un formulario o un control contenedor.  
  
-   Llamar a un método personalizado para validar los datos en los controles de forma manual.  
  
#### <a name="default-implicit-validation-behavior-for-windows-forms-controls"></a>Controles de comportamiento predeterminado de la validación implícita de Windows Forms  
 Distintos controles de formularios Windows Forms tienen valores predeterminados diferentes para sus <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> propiedad. La siguiente tabla muestra los controles más comunes y sus valores predeterminados.  
  
|Control|Comportamiento de validación predeterminado|  
|-------------|---------------------------------|  
|<xref:System.Windows.Forms.ContainerControl>|<xref:System.Windows.Forms.AutoValidate.Inherit>|  
|<xref:System.Windows.Forms.Form>|<xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>|  
|<xref:System.Windows.Forms.PropertyGrid>|Propiedad no expuesta en Visual Studio|  
|<xref:System.Windows.Forms.ToolStripContainer>|Propiedad no expuesta en Visual Studio|  
|<xref:System.Windows.Forms.SplitContainer>|<xref:System.Windows.Forms.AutoValidate.Inherit>|  
|<xref:System.Windows.Forms.UserControl>|<xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>|  
  
## <a name="closing-the-form-and-overriding-validation"></a>Cerrar el formulario y reemplazar la validación  
 Cuando un control conserva el foco porque los datos que contiene son válidos, es imposible cerrar el formulario principal en una de las maneras habituales:  
  
-   Haciendo clic en el **cerrar** botón.  
  
-   Si selecciona **cerrar** en el **System** menú.  
  
-   Mediante una llamada a la <xref:System.Windows.Forms.Form.Close%2A> método mediante programación.  
  
 Sin embargo, en algunos casos, puede permitir al usuario cerrar el formulario independientemente de si son válidos los valores de los controles. Puede reemplazar la validación y cerrar un formulario que contenga datos no válidos mediante la creación de un controlador para el formulario <xref:System.Windows.Forms.Form.Closing> eventos. En el evento, establezca la <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> propiedad `false`. Esto obliga al formulario a cerrarse. Para obtener más información y un ejemplo, vea <xref:System.Windows.Forms.Form.Closing?displayProperty=nameWithType>.  
  
> [!NOTE]
>  Si se fuerza al formulario a cerrarse de esta manera, se perderán los datos en los controles del formulario que no se ha guardado. Además, los formularios modales no validan el contenido de los controles cuando se cierran. Todavía puede utilizar la validación de control para bloquear el foco a un control, pero no es necesario preocuparse por el comportamiento asociado al cerrar el formulario.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.Control.Validating?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Form.Closing?displayProperty=nameWithType>  
 <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType>  
 [MaskedTextBox (control)](../../../docs/framework/winforms/controls/maskedtextbox-control-windows-forms.md)  
 [Ejemplos de expresiones regulares](../../../docs/standard/base-types/regular-expression-examples.md)
