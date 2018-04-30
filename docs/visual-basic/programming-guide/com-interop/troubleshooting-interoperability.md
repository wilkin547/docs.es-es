---
title: Solucionar problemas de interoperabilidad (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- interop, deploying assemblies
- assemblies [Visual Basic]
- interop, installing assemblies that share components
- COM objects, troubleshooting
- interop, sharing components
- troubleshooting interoperability [Visual Basic]
- interoperability, troubleshooting
- COM interop [Visual Basic], troubleshooting
- assemblies [Visual Basic], deploying
- troubleshooting Visual Basic, interoperability
- interop assemblies
- interoperability, sharing components
- shared components, using with assemblies
ms.assetid: b324cc1e-b03c-4f39-aea6-6a6d5bfd0e37
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f3ff175a0f8d152febf2d50c294d401b12285fc7
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="troubleshooting-interoperability-visual-basic"></a>Solucionar problemas de interoperabilidad (Visual Basic)
Cuando se interoperar entre COM y el código administrado de la [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], pueden surgir uno o varios de los siguientes problemas comunes.  
  
##  <a name="vbconinteroperabilitymarshalinganchor1"></a> Serialización de interoperabilidad  
 En ocasiones, quizá deba utilizar tipos de datos que no son parte de la [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. Ensamblados de interoperabilidad controlan la mayor parte del trabajo para objetos COM, pero puede que tenga que controlar los tipos de datos que se usan cuando los objetos administrados se exponen a COM. Por ejemplo, las estructuras en bibliotecas de clases deben especificar el `BStr` no administrada de tipo en las cadenas enviadas a los objetos COM creados con Visual Basic 6.0 y versiones anteriores. En tales casos, puede usar el <xref:System.Runtime.InteropServices.MarshalAsAttribute> atributo para los tipos administrados se exponga como tipos no administrados.  
  
##  <a name="vbconinteroperabilitymarshalinganchor2"></a> Exportar cadenas de longitud fija a código no administrado  
 En Visual Basic 6.0 y versiones anteriores, las cadenas se exportan a objetos COM como secuencias de bytes sin un carácter de terminación null. Por compatibilidad con otros lenguajes, Visual Basic .NET incluye un carácter de terminación al exportar cadenas. La mejor manera de solucionar esta incompatibilidad es exportar cadenas que no tienen el carácter de terminación como matrices de `Byte` o `Char`.  
  
##  <a name="vbconinteroperabilitymarshalinganchor3"></a> Exportar jerarquías de herencia  
 Jerarquías desaparecen cuando se exponen como objetos COM de clase administrada. Por ejemplo, si define una clase base con un miembro y, a continuación, heredar la clase base en una clase derivada que se expone como un objeto COM, los clientes que utilizan la clase derivada en el objeto COM no podrá usar a los miembros heredados. Miembros de clase base pueden tener acceso desde los objetos COM como instancias de una clase base y, a continuación, solo si la clase base también se crea como un objeto COM.  
  
## <a name="overloaded-methods"></a>Métodos sobrecargados  
 Aunque puede crear métodos sobrecargados con Visual Basic, no son compatibles con COM. Cuando una clase que contiene métodos sobrecargados se expone como un objeto COM, se generan nombres de método nuevos para los métodos sobrecargados.  
  
 Por ejemplo, considere una clase que tiene dos sobrecargas de la `Synch` método. Cuando la clase se expone como un objeto COM, los nuevos nombres de método generados pudieron ser `Synch` y `Synch_2`.  
  
 El cambio de nombre puede producir dos problemas para los consumidores del objeto COM.  
  
1.  Los clientes no pueden esperar que los nombres de método generados.  
  
2.  Los nombres de método generados en la clase expuesta como un objeto COM pueden cambiar cuando se agregan nuevas sobrecargas a la clase o su clase base. Esto puede causar problemas de control de versiones.  
  
 Para resolver ambos problemas, asigne a cada método un nombre único, en lugar de utilizar la sobrecarga, cuando desarrolle objetos que se expondrán como objetos COM.  
  
##  <a name="vbconinteroperabilitymarshalinganchor4"></a> Uso de objetos COM mediante ensamblados de interoperabilidad  
 Usar ensamblados de interoperabilidad casi como si fueran equivalentes de código administrado para los objetos COM que representan. Sin embargo, dado que son contenedores y no objetos COM reales, hay algunas diferencias entre el uso de ensamblados de interoperabilidad y ensamblados estándar. Estas áreas de diferencia incluyen la exposición de las clases y los tipos de datos de parámetros y valores devueltos.  
  
##  <a name="vbconinteroperabilitymarshalinganchor5"></a> Clases expuestas como ambas Interfaces y clases  
 A diferencia de las clases de ensamblados estándares, las clases COM se exponen en los ensamblados de interoperabilidad como una interfaz y una clase que representa la clase COM. Nombre de la interfaz es idéntico de la clase COM. El nombre de la clase de interoperabilidad es el mismo que el de la clase COM original, pero con la palabra "Class" anexada. Por ejemplo, suponga que tiene un proyecto con una referencia a un ensamblado de interoperabilidad para un objeto COM. Si la clase COM se denomina `MyComClass`, IntelliSense y el Examinador de objetos muestran una interfaz denominada `MyComClass` y una clase denominada `MyComClassClass`.  
  
##  <a name="vbconinteroperabilitymarshalinganchor6"></a> Creación de instancias de una clase de .NET Framework  
 Por lo general, se crea una instancia de un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] clase utilizando el `New` instrucción con un nombre de clase. Una clase COM representada por un ensamblado de interoperabilidad es el caso en que se puede utilizar el `New` instrucción con una interfaz. Si no utiliza la clase COM con una `Inherits` (instrucción), puede utilizar la interfaz tal como lo haría en una clase. El código siguiente muestra cómo crear un `Command` objeto en un proyecto que tiene una referencia al objeto COM de Microsoft ActiveX Data Objects 2.8 Library:  
  
 [!code-vb[VbVbalrInterop#20](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_1.vb)]  
  
 Sin embargo, si está utilizando la clase COM como base para una clase derivada, debe utilizar la clase de interoperabilidad que representa la clase COM, como en el código siguiente:  
  
 [!code-vb[VbVbalrInterop#21](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_2.vb)]  
  
> [!NOTE]
>  Ensamblados de interoperabilidad implementan implícitamente interfaces que representan las clases COM. No debe intentar usar el `Implements` dará como resultado la instrucción para implementar estas interfaces o un error.  
  
##  <a name="vbconinteroperabilitymarshalinganchor7"></a> Tipos de datos para los parámetros y valores devueltos  
 A diferencia de los miembros de los ensamblados estándar, los miembros del ensamblado de interoperabilidad pueden tener tipos de datos que difieren de aquéllos utilizados en la declaración del objeto original. Aunque los ensamblados de interoperabilidad convierten implícitamente los tipos COM en tipos compatibles con common language runtime, debe prestar atención a los tipos de datos que se usan en los dos lados para evitar errores en tiempo de ejecución. Por ejemplo, en los objetos COM creados en Visual Basic 6.0 y versiones anteriores, los valores de tipo `Integer` supone la [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] tipo equivalente, `Short`. Se recomienda que utilice el Examinador de objetos para examinar las características de los miembros importados antes de usarlos.  
  
##  <a name="vbconinteroperabilitymarshalinganchor8"></a> Métodos de COM de nivel de módulo  
 Mayoría de los objetos COM se utiliza creando una instancia de una clase COM utilizando el `New` palabra clave y, a continuación, llamar a métodos del objeto. Una excepción a esta regla implica objetos COM que contienen `AppObj` o `GlobalMultiUse` clases COM. Estas clases son similares a los métodos de nivel de módulo en clases de Visual Basic. NET. Visual Basic 6.0 y versiones anteriores crean implícitamente instancias de estos objetos la primera vez que se llame a uno de sus métodos. Por ejemplo, en Visual Basic 6.0 puede agregar una referencia a la biblioteca de objetos de Microsoft DAO 3.6 y llamar a la `DBEngine` método sin crear primero una instancia:  
  
```vb  
Dim db As DAO.Database  
' Open the database.  
Set db = DBEngine.OpenDatabase("C:\nwind.mdb")  
' Use the database object.  
```  
  
 Visual Basic .NET requiere que siempre se creen instancias de objetos COM para poder usar sus métodos. Para usar estos métodos en Visual Basic, declare una variable de la clase deseada y utilice la palabra clave new para asignar el objeto a la variable de objeto. El `Shared` palabra clave puede utilizarse cuando desee asegurarse de que se crea que solo una instancia de la clase.  
  
 [!code-vb[VbVbalrInterop#23](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_3.vb)]  
  
##  <a name="vbconinteroperabilitymarshalinganchor9"></a> Errores no controlados en controladores de eventos  
 Un problema habitual de interoperabilidad implica errores en los controladores de eventos que controlen los eventos generados por objetos COM. Estos errores se omiten a menos que busque específicamente errores con `On Error` o `Try...Catch...Finally` las instrucciones. Por ejemplo, el siguiente ejemplo es de un proyecto de Visual Basic .NET que tiene una referencia al objeto COM de Microsoft ActiveX Data Objects 2.8 Library.  
  
 [!code-vb[VbVbalrInterop#24](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_4.vb)]  
  
 Este ejemplo genera un error como se esperaba. Sin embargo, si intenta el mismo ejemplo sin el `Try...Catch...Finally` bloque, el error se omite como si usa el `OnError Resume Next` instrucción. Sin control de errores, la división por cero en modo silencioso se produce un error. Dado que tales errores nunca producen errores de excepción no controlada, es importante que use alguna forma de control de excepciones en los controladores de eventos que controlan los eventos de objetos COM.  
  
### <a name="understanding-com-interop-errors"></a>Descripción de los errores de interoperabilidad COM  
 Sin control de errores, las llamadas de interoperabilidad suelen generan errores que proporcionan poca información. Siempre que sea posible, utilice para proporcionar más información acerca de los problemas cuando se producen de control de errores estructurado. Esto puede resultar especialmente útil al depurar las aplicaciones. Por ejemplo:  
  
 [!code-vb[VbVbalrInterop#25](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_5.vb)]  
  
 Puede encontrar información como la descripción del error, HRESULT y el origen de los errores COM examinando el contenido del objeto de excepción.  
  
##  <a name="vbconinteroperabilitymarshalinganchor10"></a> Problemas con el Control ActiveX  
 Mayoría de los controles ActiveX que funcionan con Visual Basic 6.0 trabajar con Visual Basic .NET sin problemas. Las excepciones principales son controles de contenedor o controles que contienen visualmente a otros controles. Algunos ejemplos de controles más antiguos que no funcionan correctamente con [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] son los siguientes:  
  
-   Control de marco de Microsoft Forms 2.0  
  
-   Control de flechas, también conocido como el control de número  
  
-   Control Tab Sheridan  
  
 Hay solo unas soluciones para problemas de control de ActiveX no admitidos. Puede migrar los controles existentes para [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] si usted es el propietario del código fuente original. En caso contrario, puede comprobar con proveedores de software para actualizar. NET-compatible con las versiones de controles para reemplazar no admite controles ActiveX.  
  
##  <a name="vbconinteroperabilitymarshalinganchor11"></a> Pasar propiedades ReadOnly de controles ByRef  
 Visual Basic .NET produce a veces errores COM como "Error 0x800A017F CTL_E_SETNOTSUPPORTED", al pasar `ReadOnly` propiedades de algunos controles ActiveX antiguos como `ByRef` parámetros a otros procedimientos. Llamadas de procedimiento similares desde Visual Basic 6.0 no generará un error, y los parámetros se tratan como si pasaran por un valor. El mensaje de error de Visual Basic .NET indica que está intentando cambiar una propiedad que no tiene una propiedad `Set` procedimiento.  
  
 Si tiene acceso al procedimiento que se llama, puede evitar este error mediante el `ByVal` palabra clave para declarar parámetros que acepten `ReadOnly` propiedades. Por ejemplo:  
  
 [!code-vb[VbVbalrInterop#26](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_6.vb)]  
  
 Si no tiene acceso al código fuente para el procedimiento que se llama, puede forzar la propiedad que se va a pasarse por valor mediante la adición de un conjunto adicional de corchetes con el procedimiento que realiza la llamada. Por ejemplo, en un proyecto que tiene una referencia al objeto COM de Microsoft ActiveX Data Objects 2.8 Library, puede usar:  
  
 [!code-vb[VbVbalrInterop#27](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_7.vb)]  
  
##  <a name="vbconinteroperabilitymarshalinganchor12"></a> Implementar ensamblados que expongan interoperabilidad  
 Implementar ensamblados que expongan interfaces COM presenta algunos desafíos únicos. Por ejemplo, un posible problema se produce cuando aplicaciones independientes hacen referencia al mismo ensamblado COM. Esta situación es habitual cuando se instala una nueva versión de un ensamblado y otra aplicación sigue usando la versión anterior del ensamblado. Si desinstala un ensamblado que comparta un archivo DLL, puede involuntariamente hace disponible para los demás ensamblados.  
  
 Para evitar este problema, debe instalar a ensamblados compartidos en la caché Global de ensamblados (GAC) y usar un módulo de combinación para el componente. Si no se puede instalar la aplicación en la GAC, debe instalarse en CommonFilesFolder en un subdirectorio específico de la versión.  
  
 Los ensamblados compartidos no deben estar en paralelo en el directorio con la aplicación que realiza la llamada.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [Interoperabilidad COM](../../../visual-basic/programming-guide/com-interop/index.md)  
 [TlbImp.exe (Importador de la biblioteca de tipos)](../../../framework/tools/tlbimp-exe-type-library-importer.md)  
 [Tlbexp.exe (Exportador de la biblioteca de tipos)](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d)  
 [Tutorial: Implementación de la herencia mediante objetos COM](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
 [Inherits (instrucción)](../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [Caché global de ensamblados](../../../framework/app-domains/gac.md)
