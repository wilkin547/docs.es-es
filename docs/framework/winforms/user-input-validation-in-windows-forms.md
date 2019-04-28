---
title: Validación de los datos proporcionados por el usuario en formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, validating user input
- validation [Windows Forms], Windows Forms user input
- user input [Windows Forms], validating in Windows Forms
- validating user input [Windows Forms], Windows Forms
ms.assetid: 4ec07681-1dee-4bf9-be5e-718f635a33a1
ms.openlocfilehash: c8a40706df4274728b438cff2539173a0e94b767
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61800131"
---
# <a name="user-input-validation-in-windows-forms"></a>Validación de los datos proporcionados por el usuario en formularios Windows Forms
Cuando los usuarios escriben datos en la aplicación, desea comprobar que los datos son válidos antes de que lo usa la aplicación. Puede requerir que determinados campos de texto no sea de longitud cero, que tenga formato de un campo como un número de teléfono u otro tipo de datos con formato correcto o que una cadena no contiene caracteres no seguros que podrían usarse para poner en peligro la seguridad de una base de datos. Windows Forms proporciona varias maneras de validar la entrada en la aplicación.  
  
## <a name="validation-with-the-maskedtextbox-control"></a>Validación con el Control MaskedTextBox  
 Si es necesario que los usuarios escriban datos en un formato bien definido, como un número de teléfono o un número de pieza, puede hacerlo rápidamente y con un mínimo de código mediante el uso de la <xref:System.Windows.Forms.MaskedTextBox> control. Un *máscara* es una cadena formada por caracteres de un lenguaje de enmascaramiento que especifica los caracteres que se pueden escribir en cualquier posición dada en el cuadro de texto. El control muestra un conjunto de mensajes al usuario. Si el usuario escribe una entrada incorrecta, por ejemplo, el usuario escribe una letra cuando se requiere un dígito, el control rechazará automáticamente la entrada.  
  
 El lenguaje de enmascaramiento que se usa por <xref:System.Windows.Forms.MaskedTextBox> es muy flexible. Permite especificar caracteres requeridos, caracteres opcionales, caracteres literales, como guiones y paréntesis, caracteres de divisa y separadores de fecha. El control también funciona bien cuando se enlaza a un origen de datos. El <xref:System.Windows.Forms.Binding.Format> eventos en un enlace de datos se pueden usar para volver a formatear los datos entrantes para cumplir con la máscara y el <xref:System.Windows.Forms.Binding.Parse> evento puede utilizarse para volver a formatear los datos salientes para cumplir con las especificaciones del campo de datos.  
  
 Para obtener más información, consulte [MaskedTextBox Control](./controls/maskedtextbox-control-windows-forms.md).  
  
## <a name="event-driven-validation"></a>Validación controlada por eventos  
 Si desea tener control completo mediante programación a través de la validación, o necesita realizar comprobaciones de validación compleja, debe usar los eventos de validación integrados en la mayoría de los controles de Windows Forms. Cada control que acepta la entrada de usuario de forma libre tiene un <xref:System.Windows.Forms.Control.Validating> evento que se producirá cada vez que el control requiere validación de datos. En el <xref:System.Windows.Forms.Control.Validating> el método de control de eventos, puede validar entrada de varias maneras de usuario. Por ejemplo, si tiene un cuadro de texto que debe contener un código postal, puede realizar la validación de las maneras siguientes:  
  
- Si el código postal debe pertenecer a un grupo específico de códigos postales, puede realizar una comparación de cadenas en la entrada para validar los datos introducidos por el usuario. Por ejemplo, si el código postal debe estar en el conjunto {10001, 10002, 10003}, puede usar una comparación de cadenas para validar los datos.  
  
- Si el código postal debe estar en un formulario específico puede utilizar expresiones regulares para validar los datos introducidos por el usuario. Por ejemplo, para validar el formato `#####` o `#####-####`, puede usar la expresión regular `^(\d{5})(-\d{4})?$`. Para validar el formulario `A#A #A#`, puede usar la expresión regular `[A-Z]\d[A-Z] \d[A-Z]\d`. Para obtener más información sobre las expresiones regulares, vea [expresiones regulares de .NET Framework](../../standard/base-types/regular-expressions.md) y [ejemplos de expresiones regulares](../../standard/base-types/regular-expression-examples.md).  
  
- Si el código postal debe ser un código postal de Estados Unidos, podría llamar a un servicio Web de código postal para validar los datos introducidos por el usuario.  
  
 El <xref:System.Windows.Forms.Control.Validating> evento se proporciona un objeto de tipo <xref:System.ComponentModel.CancelEventArgs>. Si determina que los datos del control no sean válidos, puede cancelar el <xref:System.Windows.Forms.Control.Validating> eventos mediante el establecimiento de este objeto <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> propiedad `true`. Si no establece la <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> propiedad, Windows Forms asumirá que la validación se realizó correctamente para ese control y generar el <xref:System.Windows.Forms.Control.Validated> eventos.  
  
 Para obtener un ejemplo de código que valida una dirección de correo electrónico en un <xref:System.Windows.Controls.TextBox>, consulte <xref:System.Windows.Forms.Control.Validating>.  
  
### <a name="data-binding-and-event-driven-validation"></a>Enlace de datos y validación controlada por eventos  
 Validación es muy útil cuando ha enlazado sus controles a un origen de datos, como una tabla de base de datos. Mediante la validación, puede asegurarse de que los datos del control cumplen el formato requerido por el origen de datos y que no contienen caracteres especiales, como las comillas y realizar una copia de las barras diagonales podrían no ser seguro.  
  
 Cuando se usa el enlace de datos, los datos en el control se sincronizan con el origen de datos durante la ejecución de la <xref:System.Windows.Forms.Control.Validating> eventos. Si cancela el <xref:System.Windows.Forms.Control.Validating> eventos, los datos no se sincronizarán con el origen de datos.  
  
> [!IMPORTANT]
>  Si dispone de validación personalizada que tiene lugar después de la <xref:System.Windows.Forms.Control.Validating> eventos, no afectará el enlace de datos. Por ejemplo, si tiene código en un <xref:System.Windows.Forms.Control.Validated> eventos que se intenta cancelar el enlace de datos, se seguirá produciendo el enlace de datos. En este caso, para realizar la validación en el <xref:System.Windows.Forms.Control.Validated> eventos, cambie el control **modo de actualización del origen de datos** propiedad (**bajo (Databindings)**\\ **(avanzado)** ) desde **OnValidation** a **nunca**y agregue *Control*`.DataBindings["`*\<SUCAMPO >*  `"].WriteValue()` para el código de validación.  
  
### <a name="implicit-and-explicit-validation"></a>Validación implícita y explícita  
 ¿Por lo que si los datos de un control se validarán? Esto depende de usted, el desarrollador. Puede utilizar la validación implícita o explícita, según las necesidades de su aplicación.  
  
#### <a name="implicit-validation"></a>Validación implícita  
 El enfoque de validación implícita valida los datos cuando el usuario escriba. Puede validar los datos como los datos se escriben en un control mediante la lectura de las claves de medida que se presionan, o incluso más comúnmente siempre que el usuario tiene el foco de entrada de un control y se desplaza a la siguiente. Este enfoque es útil cuando desea dar al usuario información inmediata acerca de los datos mientras trabajan.  
  
 Si desea utilizar la validación implícita de un control, debe establecer ese control <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> propiedad `true`. Si cancela la <xref:System.Windows.Forms.Control.Validating> evento, el comportamiento del control vendrá determinado por el valor que se ha asignado a <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A>. Si ha asignado <xref:System.Windows.Forms.AutoValidate.EnablePreventFocusChange>, si se cancela el evento el <xref:System.Windows.Forms.Control.Validated> eventos no que se produzca. Foco de entrada permanecerá en el control actual hasta que el usuario cambia los datos a una entrada válida. Si ha asignado <xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>, el <xref:System.Windows.Forms.Control.Validated> evento no se producirá cuando se cancela el evento, pero el foco seguirá cambiando al siguiente control.  
  
 Asignar <xref:System.Windows.Forms.AutoValidate.Disable> a la <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> propiedad evita que la validación implícita por completo. Para validar los controles, tendrá que utilizar la validación explícita.  
  
#### <a name="explicit-validation"></a>Validación explícita  
 El enfoque de validación explícita valida los datos al mismo tiempo. Puede validar los datos en respuesta a una acción del usuario, como hacer clic en un botón de guardar o un vínculo siguiente. Cuando se produce la acción del usuario, puede desencadenar la validación explícita en una de las maneras siguientes:  
  
- Llame a <xref:System.Windows.Forms.ContainerControl.Validate%2A> para validar el último control que ha perdido el foco.  
  
- Llame a <xref:System.Windows.Forms.ContainerControl.ValidateChildren%2A> para validar todos los controles secundarios en un control de formulario o contenedor.  
  
- Llamar a un método personalizado para validar los datos en los controles manualmente.  
  
#### <a name="default-implicit-validation-behavior-for-windows-forms-controls"></a>Controles de comportamiento predeterminado de la validación implícita de Windows Forms  
 Diferentes controles de Windows Forms tienen valores predeterminados diferentes para sus <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> propiedad. La tabla siguiente muestran los controles más comunes y sus valores predeterminados.  
  
|Control|Comportamiento de validación predeterminado|  
|-------------|---------------------------------|  
|<xref:System.Windows.Forms.ContainerControl>|<xref:System.Windows.Forms.AutoValidate.Inherit>|  
|<xref:System.Windows.Forms.Form>|<xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>|  
|<xref:System.Windows.Forms.PropertyGrid>|Propiedad que no se exponen en Visual Studio|  
|<xref:System.Windows.Forms.ToolStripContainer>|Propiedad que no se exponen en Visual Studio|  
|<xref:System.Windows.Forms.SplitContainer>|<xref:System.Windows.Forms.AutoValidate.Inherit>|  
|<xref:System.Windows.Forms.UserControl>|<xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>|  
  
## <a name="closing-the-form-and-overriding-validation"></a>Cerrando el formulario y reemplazar la validación  
 Cuando un control mantiene el foco porque los datos que contiene no están válidos, es imposible cerrar el formulario principal en una de las formas habituales:  
  
- Al hacer clic en el **cerrar** botón.  
  
- Seleccionando **cerrar** en el **sistema** menú.  
  
- Mediante una llamada a la <xref:System.Windows.Forms.Form.Close%2A> método mediante programación.  
  
 Sin embargo, en algunos casos, puede dejar que el usuario cierra el formulario, independientemente de si son válidos los valores de los controles. Puede invalidar la validación y cerrar un formulario que contenga datos no válidos mediante la creación de un controlador para el formulario <xref:System.Windows.Forms.Form.Closing> eventos. En el evento, establezca la <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> propiedad `false`. Esto obliga al formulario a cerrarse. Para obtener más información y un ejemplo, vea <xref:System.Windows.Forms.Form.Closing?displayProperty=nameWithType>.  
  
> [!NOTE]
>  Si se fuerza al formulario a cerrarse de esta manera, se perderán los datos en los controles del formulario que no se ha guardado. Además, los formularios modales no validan el contenido de los controles cuando se cierran. Todavía puede utilizar la validación de control para bloquear el foco a un control, pero no tiene que preocuparse sobre el comportamiento asociado al cerrar el formulario.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Control.Validating?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Form.Closing?displayProperty=nameWithType>
- <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType>
- [MaskedTextBox (control)](./controls/maskedtextbox-control-windows-forms.md)
- [Ejemplos de expresiones regulares](../../standard/base-types/regular-expression-examples.md)
