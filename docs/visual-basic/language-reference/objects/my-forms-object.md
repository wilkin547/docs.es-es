---
title: "My.Forms (Objeto) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "My.Forms"
  - "My.MyProject.Forms"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Forms (objeto)"
ms.assetid: f6bff4e6-6769-4294-956b-037aa6106d2a
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# My.Forms (Objeto)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Suministra las propiedades para tener acceso a una instancia de cada formulario Windows Forms declarada en el proyecto actual.  
  
## Comentarios  
 El objeto `My.Forms` proporciona una instancia de cada formulario en el proyecto actual.  El nombre de la propiedad es igual que el nombre del formulario al que la propiedad tiene acceso.  Para obtener información sobre cómo agregar formularios a un proyecto, vea [How to: Add Windows Forms to a Project](http://msdn.microsoft.com/es-es/3d7bb25f-fd90-47cf-9378-fa0d764686c1).  
  
 Puede tener acceso a los formularios proporcionados por el objeto `My.Forms` utilizando el nombre del formulario, sin la calificación.  Como el nombre de la propiedad es igual que el del tipo de formulario, se puede tener acceso a un formulario tal como si tuviera una instancia predeterminada.  Por ejemplo, `My.Forms.Form1.Show` es equivalente a `Form1.Show`.  
  
 El objeto `My.Forms` expone sólo los formularios asociados al proyecto actual.  No proporciona acceso a formularios declarados en archivos DLL a los que se hace referencia.  Para tener acceso a un formulario que un archivo DLL proporciona, debe utilizar el nombre completo del formulario, escrito como *nombreDeDll*.*nombreDeFormulario*.  
  
 Puede utilizar la propiedad <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> para obtener una colección de los formularios abiertos de toda la aplicación.  
  
 El objeto y sus propiedades sólo están disponibles para las aplicaciones para Windows.  
  
## Propiedades  
 Cada propiedad del objeto `My.Forms` proporciona acceso a una instancia de un formulario en el proyecto actual.  El nombre de la propiedad es el mismo que el del formulario al que la propiedad tiene acceso y el tipo de propiedad es igual que el tipo de formulario.  
  
> [!NOTE]
>  Si hay un conflicto de nombres, el nombre de la propiedad para tener acceso a un formulario es *espacioDeNombresRaíz*\_*espacioDeNombres*\_*nombreDeFormulario*.  Por ejemplo, considere dos formularios denominados `Form1.` Si uno de ellos está en el espacio de nombres raíz `WindowsApplication1` y en el espacio de nombres `Namespace1`, se tendría acceso a ese formulario a través de `My.Forms.WindowsApplication1_Namespace1_Form1`.  
  
 El objeto `My.Forms` proporciona acceso a la instancia del formulario principal de la aplicación que se creó en el inicio.  Para todos los demás formularios, el objeto `My.Forms` crea una nueva instancia del formulario cuando se tiene acceso al mismo y la almacena.  Los intentos siguientes de acceso a la propiedad devuelven esa instancia del formulario.  
  
 Puede desechar un formulario asignando `Nothing` a la propiedad para ese formulario.  El establecedor de la propiedad llama al método <xref:System.Windows.Forms.Form.Close%2A> del formulario y, a continuación, asigna `Nothing` al valor almacenado.  Si se asigna un valor distinto de `Nothing` a la propiedad, el establecedor produce una excepción <xref:System.ArgumentException>.  
  
 Puede probar si una propiedad del objeto `My.Forms` almacena una instancia del formulario mediante el operador `Is` o `IsNot`.  Puede utilizar esos operadores para comprobar si el valor de la propiedad es `Nothing`.  
  
> [!NOTE]
>  Normalmente, el operador `Is` o `IsNot` tiene que leer el valor de la propiedad para realizar la comparación.  Sin embargo, si la propiedad almacena actualmente `Nothing`, crea una nueva instancia del formulario y, a continuación, devuelve esa instancia.  No obstante, el compilador de Visual Basic trata las propiedades del objeto `My.Forms` de forma diferente y permite al operador `Is` o `IsNot` comprobar el estado de la propiedad sin cambiar su valor.  
  
## Ejemplo  
 Este ejemplo cambia el título del formulario `SidebarMenu` predeterminado.  
  
 [!code-vb[VbVbalrMyForms#2](../../../visual-basic/language-reference/objects/codesnippet/visualbasic/my-forms-object_1.vb)]  
  
 Para que este ejemplo funcione, el proyecto debe tener un formulario denominado `SidebarMenu`.  Para obtener más información, vea [How to: Add Windows Forms to a Project](http://msdn.microsoft.com/es-es/3d7bb25f-fd90-47cf-9378-fa0d764686c1).  
  
 Este código sólo funcionará en un proyecto de aplicación para Windows.  
  
## Requisitos  
  
### Disponibilidad por tipo de proyecto  
  
|||  
|-|-|  
|Tipo de proyecto|Disponible|  
|Aplicación Windows|**Sí**|  
|Biblioteca de clases|No|  
|Aplicación de consola|No|  
|Biblioteca de controles de Windows|No|  
|Biblioteca de controles Web|No|  
|Servicio de Windows|No|  
|Sitio Web|No|  
  
## Vea también  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>   
 <xref:System.Windows.Forms.Form>   
 <xref:System.Windows.Forms.Form.Close%2A>   
 [Objetos](../../../visual-basic/language-reference/objects/index.md)   
 [How to: Add Windows Forms to a Project](http://msdn.microsoft.com/es-es/3d7bb25f-fd90-47cf-9378-fa0d764686c1)   
 [Is \(Operador\)](../../../visual-basic/language-reference/operators/is-operator.md)   
 [IsNot \(Operador\)](../../../visual-basic/language-reference/operators/isnot-operator.md)   
 [Acceso a los formularios de la aplicación](../../../visual-basic/developing-apps/programming/accessing-application-forms.md)