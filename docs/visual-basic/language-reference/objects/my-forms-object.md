---
title: My.Forms (objeto) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.Forms
- My.MyProject.Forms
helpviewer_keywords:
- My.Forms object
ms.assetid: f6bff4e6-6769-4294-956b-037aa6106d2a
ms.openlocfilehash: d15765b7673f321d4362ceea0adb73959a7e7726
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/11/2018
ms.locfileid: "44360484"
---
# <a name="myforms-object"></a>My.Forms (Objeto)
Proporciona propiedades para tener acceso a una instancia de cada formulario de Windows que se declara en el proyecto actual.  
  
## <a name="remarks"></a>Comentarios  
 La `My.Forms` objeto proporciona una instancia de cada formulario en el proyecto actual. El nombre de la propiedad es el mismo que el nombre del formulario que tiene acceso la propiedad.   
  
 Puede tener acceso a los formularios proporcionados por el `My.Forms` objeto con el nombre del formulario, sin calificación. Dado que el nombre de propiedad es igual al nombre de tipo del formulario, esto le permite tener acceso a un formulario como si tuviera una instancia predeterminada. Por ejemplo, `My.Forms.Form1.Show` es equivalente a `Form1.Show`.  
  
 La `My.Forms` objeto expone sólo los formularios asociados al proyecto actual. No proporciona acceso a formularios declarados en archivos DLL que se hace referencia. Para obtener acceso a un formulario que proporciona un archivo DLL, debe usar el nombre completo del formulario, escrito como *DllName*. *FormName*.  
  
 Puede usar el <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> propiedad para obtener una colección de los formularios abiertos de toda la aplicación.  
  
 El objeto y sus propiedades están disponibles solo para las aplicaciones de Windows.  
  
## <a name="properties"></a>Propiedades  
 Cada propiedad de la `My.Forms` objeto proporciona acceso a una instancia de un formulario en el proyecto actual. El nombre de la propiedad es el mismo que el nombre del formulario que tiene acceso la propiedad y el tipo de propiedad es el mismo que el tipo de formulario.  
  
> [!NOTE]
>  Si hay un conflicto de nombres, el nombre de propiedad para tener acceso a un formulario es *RootNamespace*_*Namespace*\_*FormName*. Por ejemplo, considere dos formularios denominados `Form1.`si uno de estos formularios está en el espacio de nombres raíz `WindowsApplication1` y en el espacio de nombres `Namespace1`, accedería a ese formulario a través de `My.Forms.WindowsApplication1_Namespace1_Form1`.  
  
 La `My.Forms` objeto proporciona acceso a la instancia del formulario principal de la aplicación que se creó en el inicio. Para todas las demás formas, el `My.Forms` objeto crea una nueva instancia del formulario cuando se tiene acceso y lo almacena. Intenta obtener acceso a esa propiedad devuelva esa instancia del formulario.  
  
 Puede eliminar mediante la asignación de un formulario `Nothing` a la propiedad de ese formulario. Las llamadas de establecedor de propiedad el <xref:System.Windows.Forms.Form.Close%2A> método del formulario y, a continuación, asigna `Nothing` al valor almacenado. Si asigna cualquier valor distinto de `Nothing` a la propiedad, el establecedor produce una <xref:System.ArgumentException> excepción.  
  
 Puede probar si una propiedad de la `My.Forms` objeto almacena una instancia del formulario mediante el uso de la `Is` o `IsNot` operador. Puede usar estos operadores para comprobar si el valor de la propiedad es `Nothing`.  
  
> [!NOTE]
>  Normalmente, el `Is` o `IsNot` operador tiene que leer el valor de la propiedad que se va a realizar la comparación. Sin embargo, si la propiedad se almacena actualmente `Nothing`, la propiedad crea una nueva instancia del formulario y, a continuación, devuelve esa instancia. Sin embargo, el compilador de Visual Basic trata las propiedades de la `My.Forms` objeto de forma diferente y permite la `Is` o `IsNot` operador para comprobar el estado de la propiedad sin cambiar su valor.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo cambia el título del valor predeterminado `SidebarMenu` formulario.  
  
 [!code-vb[VbVbalrMyForms#2](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-forms-object_1.vb)]  
  
 Para que funcione este ejemplo, el proyecto debe tener un formulario denominado `SidebarMenu`.  
  
 Este código funcionará solo en un proyecto de aplicación de Windows.  
  
## <a name="requirements"></a>Requisitos  
  
### <a name="availability-by-project-type"></a>Disponibilidad por tipo de proyecto  
  
|Tipo de proyecto|Disponible|  
|---|---|  
|Aplicación Windows|**Sí**|  
|Biblioteca de clases|No|  
|Aplicación de consola|No|  
|Biblioteca de controles de Windows|No|  
|Biblioteca de controles Web|No|  
|Servicio de Windows|No|  
|Sitio web|No|  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>  
 <xref:System.Windows.Forms.Form>  
 <xref:System.Windows.Forms.Form.Close%2A>  
 [Objects](../../../visual-basic/language-reference/objects/index.md)  
 [Is (operador)](../../../visual-basic/language-reference/operators/is-operator.md)  
 [IsNot (operador)](../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [Acceso ad los formularios de la aplicación](../../../visual-basic/developing-apps/programming/accessing-application-forms.md)
