---
title: Validación de los datos proporcionados por el usuario en formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, validating user input
- validation [Windows Forms], Windows Forms user input
- user input [Windows Forms], validating in Windows Forms
- validating user input [Windows Forms], Windows Forms
ms.assetid: 4ec07681-1dee-4bf9-be5e-718f635a33a1
ms.openlocfilehash: 2b83e94f188f46d0cedc9fed9e9c5a946ada59c5
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2019
ms.locfileid: "74960420"
---
# <a name="user-input-validation-in-windows-forms"></a>Validación de los datos proporcionados por el usuario en formularios Windows Forms
Cuando los usuarios escriben datos en la aplicación, puede que desee comprobar que los datos son válidos antes de que la aplicación los use. Es posible que necesite que determinados campos de texto no tengan una longitud cero, que un campo tenga formato de número de teléfono u otro tipo de datos con formato correcto, o que una cadena no contenga ningún carácter no seguro que pueda usarse para poner en peligro la seguridad de una base de datos. Windows Forms proporciona varias maneras de validar la entrada en la aplicación.  
  
## <a name="validation-with-the-maskedtextbox-control"></a>Validación con el control MaskedTextBox  
 Si necesita que los usuarios escriban datos en un formato bien definido, como un número de teléfono o un número de pieza, puede hacerlo rápidamente y con un código mínimo mediante el control de <xref:System.Windows.Forms.MaskedTextBox>. Una *máscara* es una cadena formada por caracteres de un lenguaje de enmascaramiento que especifica los caracteres que se pueden escribir en cualquier posición determinada en el cuadro de texto. El control muestra un conjunto de mensajes para el usuario. Si el usuario escribe una entrada incorrecta, por ejemplo, el usuario escribe una letra cuando se requiere un dígito, el control rechazará automáticamente la entrada.  
  
 El lenguaje de enmascaramiento que usa <xref:System.Windows.Forms.MaskedTextBox> es muy flexible. Permite especificar caracteres necesarios, caracteres opcionales, caracteres literales, como guiones y paréntesis, caracteres de divisa y separadores de fecha. El control también funciona bien cuando se enlaza a un origen de datos. El evento <xref:System.Windows.Forms.Binding.Format> de un enlace de datos se puede usar para volver a dar formato a los datos entrantes para que cumplan la máscara y el evento <xref:System.Windows.Forms.Binding.Parse> se puede usar para volver a dar formato a los datos salientes para cumplir las especificaciones del campo de datos.  
  
 Para obtener más información, vea [control MaskedTextBox](./controls/maskedtextbox-control-windows-forms.md).  
  
## <a name="event-driven-validation"></a>Validación controlada por eventos  
 Si desea tener un control completo mediante programación sobre la validación o necesita realizar comprobaciones de validación complejas, debe utilizar los eventos de validación integrados en la mayoría de los controles de Windows Forms. Cada control que acepta datos proporcionados por el usuario de forma libre tiene un evento <xref:System.Windows.Forms.Control.Validating> que se producirá cada vez que el control requiera la validación de datos. En el método de control de eventos <xref:System.Windows.Forms.Control.Validating>, puede validar los datos proporcionados por el usuario de varias maneras. Por ejemplo, si tiene un cuadro de texto que debe contener un código postal, puede realizar la validación de las siguientes maneras:  
  
- Si el código postal debe pertenecer a un grupo específico de códigos postales, puede realizar una comparación de cadenas en la entrada para validar los datos introducidos por el usuario. Por ejemplo, si el código postal debe estar en el conjunto {10001, 10002, 10003}, puede usar una comparación de cadenas para validar los datos.  
  
- Si el código postal debe estar en un formato específico, puede usar expresiones regulares para validar los datos especificados por el usuario. Por ejemplo, para validar el formulario `#####` o `#####-####`, puede usar la expresión regular `^(\d{5})(-\d{4})?$`. Para validar el formulario `A#A #A#`, puede usar el `[A-Z]\d[A-Z] \d[A-Z]\d`de la expresión regular. Para obtener más información sobre las expresiones regulares, vea [.NET Framework expresiones regulares](../../standard/base-types/regular-expressions.md) y [ejemplos de expresiones regulares](../../standard/base-types/regular-expression-examples.md).  
  
- Si el código postal debe ser un código postal de Estados Unidos válido, puede llamar a un servicio Web de código postal para validar los datos introducidos por el usuario.  
  
 El evento <xref:System.Windows.Forms.Control.Validating> se suministra a un objeto de tipo <xref:System.ComponentModel.CancelEventArgs>. Si determina que los datos del control no son válidos, puede cancelar el evento <xref:System.Windows.Forms.Control.Validating> estableciendo la propiedad <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> de este objeto en `true`. Si no establece la propiedad <xref:System.ComponentModel.CancelEventArgs.Cancel%2A>, Windows Forms asumirá que la validación se realizó correctamente para ese control y generará el evento <xref:System.Windows.Forms.Control.Validated>.  
  
 Para obtener un ejemplo de código que valida una dirección de correo electrónico en un <xref:System.Windows.Controls.TextBox>, vea <xref:System.Windows.Forms.Control.Validating>.  
  
### <a name="data-binding-and-event-driven-validation"></a>Enlace de datos y validación controlada por eventos  
 La validación es muy útil cuando se enlazan los controles a un origen de datos, como una tabla de base de datos. Mediante el uso de la validación, puede asegurarse de que los datos del control satisfacen el formato requerido por el origen de datos y que no contienen ningún carácter especial como comillas y barras diagonales inversas que podrían no ser seguras.  
  
 Cuando se usa el enlace de datos, los datos del control se sincronizan con el origen de datos durante la ejecución del evento <xref:System.Windows.Forms.Control.Validating>. Si cancela el evento <xref:System.Windows.Forms.Control.Validating>, los datos no se sincronizarán con el origen de datos.  
  
> [!IMPORTANT]
> Si tiene validación personalizada que tiene lugar después del evento <xref:System.Windows.Forms.Control.Validating>, no afectará al enlace de datos. Por ejemplo, si tiene código en un evento de <xref:System.Windows.Forms.Control.Validated> que intenta cancelar el enlace de datos, se seguirá produciendo el enlace de datos. En este caso, para realizar la validación en el evento <xref:System.Windows.Forms.Control.Validated>, cambie la propiedad **del modo de actualización del origen de datos** del control (**en (DataBindings)** \\ **(avanzado)** **) de la** validación a **nunca**y agregue`.DataBindings["`de *control* *\<sucampo >* a su código de validación.  
  
### <a name="implicit-and-explicit-validation"></a>Validación implícita y explícita  
 ¿Cuándo se validan los datos de un control? Este es el desarrollador. Puede usar la validación implícita o explícita, en función de las necesidades de la aplicación.  
  
#### <a name="implicit-validation"></a>Validación implícita  
 El método de validación implícita valida los datos a medida que el usuario los escribe. Puede validar los datos a medida que los datos se escriben en un control leyendo las teclas a medida que se presionan, o con mayor frecuencia cada vez que el usuario toma el foco de entrada de un control y se desplaza a la siguiente. Este enfoque es útil cuando desea proporcionar al usuario comentarios inmediatos sobre los datos mientras están trabajando.  
  
 Si desea utilizar la validación implícita para un control, debe establecer la propiedad <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> de ese control en <xref:System.Windows.Forms.AutoValidate.EnablePreventFocusChange> o <xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>. Si cancela el evento <xref:System.Windows.Forms.Control.Validating>, el comportamiento del control estará determinado por el valor asignado a <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A>. Si ha asignado <xref:System.Windows.Forms.AutoValidate.EnablePreventFocusChange>, al cancelar el evento se producirá que no se produzca el evento de <xref:System.Windows.Forms.Control.Validated>. El foco de entrada permanecerá en el control actual hasta que el usuario cambie los datos a una entrada válida. Si ha asignado <xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>, el evento de <xref:System.Windows.Forms.Control.Validated> no se producirá al cancelar el evento, pero el foco seguirá cambiado al control siguiente.  
  
 La asignación de <xref:System.Windows.Forms.AutoValidate.Disable> a la propiedad <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> evita totalmente la validación implícita. Para validar los controles, tendrá que usar la validación explícita.  
  
#### <a name="explicit-validation"></a>Validación explícita  
 El enfoque de validación explícita valida los datos al mismo tiempo. Puede validar los datos en respuesta a una acción del usuario, como hacer clic en un botón Guardar o en un vínculo siguiente. Cuando se produce la acción del usuario, puede desencadenar la validación explícita de una de las siguientes maneras:  
  
- Llame a <xref:System.Windows.Forms.ContainerControl.Validate%2A> para validar que el último control ha perdido el foco.  
  
- Llame a <xref:System.Windows.Forms.ContainerControl.ValidateChildren%2A> para validar todos los controles secundarios de un formulario o control contenedor.  
  
- Llame a un método personalizado para validar manualmente los datos de los controles.  
  
#### <a name="default-implicit-validation-behavior-for-windows-forms-controls"></a>Comportamiento de validación implícita predeterminada para controles de Windows Forms  
 Los distintos controles Windows Forms tienen valores predeterminados diferentes para su propiedad <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A>. En la tabla siguiente se muestran los controles más comunes y sus valores predeterminados.  
  
|Control|Comportamiento de validación predeterminado|  
|-------------|---------------------------------|  
|<xref:System.Windows.Forms.ContainerControl>|<xref:System.Windows.Forms.AutoValidate.Inherit>|  
|<xref:System.Windows.Forms.Form>|<xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>|  
|<xref:System.Windows.Forms.PropertyGrid>|Propiedad no expuesta en Visual Studio|  
|<xref:System.Windows.Forms.ToolStripContainer>|Propiedad no expuesta en Visual Studio|  
|<xref:System.Windows.Forms.SplitContainer>|<xref:System.Windows.Forms.AutoValidate.Inherit>|  
|<xref:System.Windows.Forms.UserControl>|<xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>|  
  
## <a name="closing-the-form-and-overriding-validation"></a>Cerrar el formulario e invalidar la validación  
 Cuando un control mantiene el foco porque los datos que contiene no son válidos, es imposible cerrar el formulario principal de una de las maneras habituales:  
  
- Haciendo clic en el botón **cerrar** .  
  
- Seleccionando **cerrar** en el menú **sistema** .  
  
- Llamando al método <xref:System.Windows.Forms.Form.Close%2A> mediante programación.  
  
 Sin embargo, en algunos casos, es posible que desee permitir que el usuario cierre el formulario independientemente de si los valores de los controles son válidos. Puede invalidar la validación y cerrar un formulario que todavía contiene datos no válidos creando un controlador para el evento <xref:System.Windows.Forms.Form.FormClosing> del formulario. En el evento, establezca la propiedad <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> en `false`. Esto fuerza el cierre del formulario. Para obtener más información y un ejemplo, vea <xref:System.Windows.Forms.Form.FormClosing?displayProperty=nameWithType>.  
  
> [!NOTE]
> Si fuerza al formulario a cerrarse de esta manera, se perderán los datos de los controles del formulario que no se hayan guardado todavía. Además, los formularios modales no validan el contenido de los controles cuando están cerrados. Todavía puede usar la validación de controles para bloquear el foco a un control, pero no tiene que preocuparse del comportamiento asociado al cierre del formulario.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Control.Validating?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Form.FormClosing?displayProperty=nameWithType>
- <xref:System.Windows.Forms.FormClosingEventArgs?displayProperty=nameWithType>
- [MaskedTextBox (control)](./controls/maskedtextbox-control-windows-forms.md)
- [Ejemplos de expresiones regulares](../../standard/base-types/regular-expression-examples.md)
