---
title: Solucionar problemas de interoperabilidad (Visual Basic) | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- interop, deploying assemblies
- assemblies [Visual Basic]
- interop, installing assemblies that share components
- COM objects, troubleshooting
- interop, sharing components
- troubleshooting interoperability
- interoperability, troubleshooting
- COM interop, troubleshooting
- assemblies [Visual Basic], deploying
- troubleshooting Visual Basic, interoperability
- interop assemblies
- interoperability, sharing components
- shared components, using with assemblies
ms.assetid: b324cc1e-b03c-4f39-aea6-6a6d5bfd0e37
caps.latest.revision: 21
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: cbc37638ed5c57b94356c2d189f36b66202ceba5
ms.lasthandoff: 03/13/2017

---
# <a name="troubleshooting-interoperability-visual-basic"></a>Solucionar problemas de interoperabilidad (Visual Basic)
Al interoperar entre COM y el código administrado de la [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)], puede encontrar uno o varios de los siguientes problemas comunes.  
  
##  <a name="vbconinteroperabilitymarshalinganchor1"></a>Cálculo de referencias de interoperabilidad  
 En ocasiones, tendrá que utilizar los tipos de datos que no son parte de la [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]. Ensamblados de interoperabilidad controlan la mayor parte del trabajo para objetos COM, pero puede que tenga que controlar los tipos de datos que se usan cuando los objetos administrados se exponen a COM. Por ejemplo, las estructuras de bibliotecas de clases deben especificar el `BStr` tipo en las cadenas enviadas a los objetos COM creados con Visual Basic 6.0 y versiones anteriores no administrado. En tales casos, puede utilizar el <xref:System.Runtime.InteropServices.MarshalAsAttribute>atributo para los tipos administrados se exponga como tipos no administrados.</xref:System.Runtime.InteropServices.MarshalAsAttribute>  
  
##  <a name="vbconinteroperabilitymarshalinganchor2"></a>Exportar cadenas de longitud fija a código no administrado  
 En Visual Basic 6.0 y versiones anteriores, las cadenas se exportan a objetos COM como secuencias de bytes sin un carácter de terminación null. Por compatibilidad con otros lenguajes, [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] incluye un carácter de terminación al exportar cadenas. La mejor manera de solucionar esta incompatibilidad es exportar cadenas sin carácter de terminación como matrices de `Byte` o `Char`.  
  
##  <a name="vbconinteroperabilitymarshalinganchor3"></a>Exportar jerarquías de herencia  
 Jerarquías desaparecen cuando se exponen como objetos COM de clase administrada. Por ejemplo, si define una clase base con un miembro y, a continuación, heredar la clase base en una clase derivada que se expone como un objeto COM, los clientes que utilizan la clase derivada en el objeto COM no pueda utilizar a los miembros heredados. Miembros de clase base pueden tener acceso desde objetos COM como instancias de una clase base y, a continuación, sólo si la clase base también se crea como un objeto COM.  
  
## <a name="overloaded-methods"></a>Métodos sobrecargados  
 Aunque puede crear varios métodos sobrecargados con [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], no son compatibles con COM. Cuando una clase que contiene métodos sobrecargados se expone como un objeto COM, se generan nombres de método nuevos para los métodos sobrecargados.  
  
 Por ejemplo, considere una clase que tiene dos sobrecargas de la `Synch` (método). Cuando la clase se expone como un objeto COM, los nuevos nombres de método generados podrían ser `Synch` y `Synch_2`.  
  
 El cambio de nombre puede producir dos problemas para los consumidores del objeto COM.  
  
1.  Los clientes no podrían esperar que los nombres de método generados.  
  
2.  Pueden cambiar los nombres de método generados en la clase expuesta como un objeto COM cuando se agregan nuevas sobrecargas a la clase o su clase base. Esto puede provocar problemas de versiones.  
  
 Para solucionar ambos problemas, asigne a cada método un nombre único, en lugar de usar la sobrecarga, cuando desarrolle objetos que se expondrán como objetos COM.  
  
##  <a name="vbconinteroperabilitymarshalinganchor4"></a>Uso de objetos COM mediante ensamblados de interoperabilidad  
 Utilizar ensamblados de interoperabilidad casi como si fueran equivalentes de código administrado para los objetos COM que representan. Sin embargo, dado que son contenedores y no objetos COM reales, hay algunas diferencias entre el uso de ensamblados de interoperabilidad y ensamblados estándar. Estas áreas de diferencia incluyen la exposición de clases y tipos de datos para parámetros y valores devueltos.  
  
##  <a name="vbconinteroperabilitymarshalinganchor5"></a>Clases expuestas como Interfaces y clases  
 A diferencia de las clases de los ensamblados estándar, las clases COM se exponen en los ensamblados de interoperabilidad como una interfaz y una clase que representa la clase COM. Nombre de la interfaz es idéntico de la clase COM. El nombre de la clase de interoperabilidad es el mismo que el de la clase COM original, pero con la palabra "Class" anexada. Por ejemplo, suponga que tiene un proyecto con una referencia a un ensamblado de interoperabilidad para un objeto COM. Si la clase COM se denomina `MyComClass`, IntelliSense y el Examinador de objetos muestran una interfaz denominada `MyComClass` y una clase denominada `MyComClassClass`.  
  
##  <a name="vbconinteroperabilitymarshalinganchor6"></a>Creación de instancias de una clase de .NET Framework  
 Generalmente, se crea una instancia de un [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] clase utilizando el `New` instrucción con un nombre de clase. Una clase COM que se representa mediante un ensamblado de interoperabilidad es el caso en que se puede utilizar el `New` instrucción con una interfaz. Si se utiliza la clase COM con una `Inherits` instrucción, puede usar la interfaz como lo haría en una clase. El código siguiente muestra cómo crear un `Command` objeto en un proyecto que tiene una referencia al objeto COM de Microsoft ActiveX Data Objects 2.8 Library:  
  
 [!code-vb[VbVbalrInterop&#20;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_1.vb)]  
  
 Sin embargo, si utiliza la clase COM como base para una clase derivada, debe utilizar la clase de interoperabilidad que representa la clase COM, como se muestra en el código siguiente:  
  
 [!code-vb[21 VbVbalrInterop](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_2.vb)]  
  
> [!NOTE]
>  Ensamblados de interoperabilidad implementan implícitamente interfaces que representan clases COM. No debe intentar usar el `Implements` dará como resultado la instrucción para implementar estas interfaces o a un error.  
  
##  <a name="vbconinteroperabilitymarshalinganchor7"></a>Tipos de datos para parámetros y valores devueltos  
 A diferencia de los miembros de los ensamblados estándar, los miembros del ensamblado de interoperabilidad pueden tener tipos de datos que difieren de aquéllos utilizados en la declaración del objeto original. Aunque los ensamblados de interoperabilidad convierten implícitamente los tipos COM en tipos compatibles con common language runtime, debe prestar atención a los tipos de datos que se usan en los dos lados para evitar errores en tiempo de ejecución. Por ejemplo, en los objetos COM creados en Visual Basic 6.0 y versiones anteriores, los valores de tipo `Integer` supone la [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] tipo equivalente, `Short`. Se recomienda que use el Examinador de objetos para examinar las características de los miembros importados antes de utilizarlos.  
  
##  <a name="vbconinteroperabilitymarshalinganchor8"></a>Métodos de COM a nivel de módulo  
 Mayoría de los objetos COM se utiliza creando una instancia de una clase COM mediante la `New` (palabra clave) y, a continuación, llamar a métodos del objeto. Una excepción a esta regla implica objetos COM que contienen `AppObj` o `GlobalMultiUse` las clases COM. Estas clases son similares a los métodos de nivel de módulo en [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] clases. Visual Basic 6.0 y versiones anteriores crean implícitamente instancias de estos objetos la primera vez que se llama a uno de sus métodos. Por ejemplo, en Visual Basic 6.0 puede agregar una referencia a la biblioteca de objetos de Microsoft DAO 3.6 y llamada la `DBEngine` método sin crear primero una instancia:  
  
```  
Dim db As DAO.Database  
' Open the database.  
Set db = DBEngine.OpenDatabase("C:\nwind.mdb")  
' Use the database object.  
```  
  
 [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)]requiere que siempre se creen instancias de objetos COM antes de poder utilizar sus métodos. Para utilizar estos métodos en [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)], declare una variable de la clase deseada y utilice la palabra clave new para asignar el objeto a la variable de objeto. El `Shared` palabra clave puede utilizarse cuando desee asegurarse de que solo una instancia de la clase se crea.  
  
 [!code-vb[23 de VbVbalrInterop #](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_3.vb)]  
  
##  <a name="vbconinteroperabilitymarshalinganchor9"></a>Errores no controlados en controladores de eventos  
 Un problema habitual de interoperabilidad implica errores en los controladores de eventos que controlan los eventos generados por objetos COM. Estos errores se omiten a menos que se registre en concreto de errores mediante `On Error` o `Try...Catch...Finally` las instrucciones. Por ejemplo, el siguiente ejemplo es de un [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] proyecto que tiene una referencia al objeto COM de Microsoft ActiveX Data Objects 2.8 Library.  
  
 [!code-vb[VbVbalrInterop&#24;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_4.vb)]  
  
 Este ejemplo genera un error como se esperaba. Sin embargo, si intenta el mismo ejemplo sin el `Try...Catch...Finally` bloque, el error se omite como si usa el `OnError Resume Next` instrucción. Sin control de errores, la división por cero generará un error silenciosamente. Dado que tales errores nunca producen errores de excepción no controlada, es importante usar algún tipo de control de excepciones en los controladores de eventos que controlan eventos de objetos COM.  
  
### <a name="understanding-com-interop-errors"></a>Descripción de los errores de interoperabilidad COM  
 Sin control de errores, llamadas de interoperabilidad suelen generan errores que proporcionan poca información. Siempre que sea posible, utilice los errores estructurado para proporcionar más información acerca de los problemas cuando se producen. Esto puede resultar especialmente útil al depurar las aplicaciones. Por ejemplo:  
  
 [!code-vb[VbVbalrInterop&#25;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_5.vb)]  
  
 Puede encontrar información como la descripción del error, HRESULT y el origen de los errores COM examinando el contenido del objeto de excepción.  
  
##  <a name="vbconinteroperabilitymarshalinganchor10"></a>Problemas de Control de ActiveX  
 La mayoría de los controles de ActiveX que funcionan con Visual Basic 6.0 funciona con [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] sin problemas. Las excepciones principales son los controles del contenedor o controles que contienen visualmente a otros controles. Algunos ejemplos de controles más antiguos que no funcionan correctamente con [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] son los siguientes:  
  
-   Microsoft Forms 2.0 Frame (control)  
  
-   Control de flechas, también conocido como control de giro  
  
-   Control Tab Sheridan  
  
 Hay sólo unas pocas soluciones para problemas de controles ActiveX no admitidos. Puede migrar controles existentes a [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] si se dispone del código fuente original. De lo contrario, puede comprobar con proveedores de software para actualizar. Versiones compatibles con NET de reemplazar los controles no admite controles ActiveX.  
  
##  <a name="vbconinteroperabilitymarshalinganchor11"></a>Pasar propiedades ReadOnly de controles ByRef  
 [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)]a veces genera errores COM como "Error 0x800A017F CTL_E_SETNOTSUPPORTED" cuando se pasa `ReadOnly` propiedades de algunos controles ActiveX antiguos como `ByRef` parámetros a otros procedimientos. Llamadas de procedimiento similares desde Visual Basic 6.0 no generan un error y los parámetros se tratan como si pasaran por valor. El mensaje de error que aparece en [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] es el objeto COM informes que está intentando cambiar una propiedad que no tiene una propiedad `Set` procedimiento.  
  
 Si tiene acceso al procedimiento que se llama, puede evitar este error mediante la `ByVal` palabra clave para declarar parámetros que acepten `ReadOnly` propiedades. Por ejemplo:  
  
 [!code-vb[26 de VbVbalrInterop #](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_6.vb)]  
  
 Si no tiene acceso al código fuente para el procedimiento que se llama, puede forzar la propiedad que se va a pasar por valor agregando un conjunto adicional de corchetes con el procedimiento que realiza la llamada. Por ejemplo, en un proyecto que tiene una referencia al objeto COM de Microsoft ActiveX Data Objects 2.8 Library, puede utilizar:  
  
 [!code-vb[VbVbalrInterop Nº&27;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_7.vb)]  
  
##  <a name="vbconinteroperabilitymarshalinganchor12"></a>Implementar ensamblados que expongan interoperabilidad  
 Implementar ensamblados que expongan interfaces COM presenta algunos desafíos únicos. Por ejemplo, se produce un posible problema si aplicaciones independientes hacen referencia al mismo ensamblado COM.. Esta situación es común cuando se instala una nueva versión de un ensamblado y otra aplicación todavía está utilizando la versión anterior del ensamblado. Si desinstala un ensamblado que comparta un archivo DLL, puede involuntariamente hacerlo disponible para otros ensamblados.  
  
 Para evitar este problema, debe instalar a ensamblados compartidos en la caché Global de ensamblados (GAC) y el componente utilice un MergeModule. Si no puede instalar la aplicación en la GAC, debe instalarse en CommonFilesFolder en un subdirectorio específico de la versión.  
  
 Los ensamblados no compartidos deben encontrarse en paralelo en el directorio de la aplicación que realiza la llamada.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute></xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Interoperabilidad COM](../../../visual-basic/programming-guide/com-interop/index.md)   
 [Tlbimp.exe (importador de la biblioteca de tipos)](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382)   
 [Tlbexp.exe (exportador de la biblioteca de tipos)](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d)   
 [Tutorial: Implementar la herencia mediante objetos COM](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)   
 [Inherits (instrucción)](../../../visual-basic/language-reference/statements/inherits-statement.md)   
 [Caché global de ensamblados](http://msdn.microsoft.com/library/cf5eacd0-d3ec-4879-b6da-5fd5e4372202)
