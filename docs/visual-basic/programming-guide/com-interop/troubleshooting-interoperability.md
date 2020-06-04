---
title: Solución de problemas de interoperabilidad
ms.date: 07/20/2015
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
ms.openlocfilehash: 0890bac80396feaf37d4ba917c1e3fafb8579981
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396771"
---
# <a name="troubleshooting-interoperability-visual-basic"></a>Solucionar problemas de interoperabilidad (Visual Basic)
Al interoperar entre COM y el código administrado del .NET Framework, puede encontrar uno o varios de los siguientes problemas comunes.  
  
## <a name="interop-marshaling"></a><a name="vbconinteroperabilitymarshalinganchor1"></a>Serialización de interoperabilidad  
 En ocasiones, puede que tenga que usar tipos de datos que no forman parte de la .NET Framework. Los ensamblados de interoperabilidad controlan la mayor parte del trabajo de los objetos COM, pero puede que tenga que controlar los tipos de datos que se utilizan cuando los objetos administrados se exponen a COM. Por ejemplo, las estructuras de las bibliotecas de clases deben especificar el `BStr` tipo no administrado en las cadenas enviadas a los objetos com creados por Visual Basic 6,0 y versiones anteriores. En tales casos, puede usar el <xref:System.Runtime.InteropServices.MarshalAsAttribute> atributo para que los tipos administrados se expongan como tipos no administrados.  
  
## <a name="exporting-fixed-length-strings-to-unmanaged-code"></a><a name="vbconinteroperabilitymarshalinganchor2"></a>Exportar cadenas de longitud fija a código no administrado  
 En Visual Basic 6,0 y versiones anteriores, las cadenas se exportan a objetos COM como secuencias de bytes sin un carácter de terminación null. Por compatibilidad con otros lenguajes, Visual Basic .NET incluye un carácter de terminación al exportar cadenas. La mejor manera de abordar esta incompatibilidad es exportar cadenas que no tienen el carácter de terminación como matrices de `Byte` o `Char` .  
  
## <a name="exporting-inheritance-hierarchies"></a><a name="vbconinteroperabilitymarshalinganchor3"></a>Exportar jerarquías de herencia  
 Las jerarquías de clases administradas se acoplan cuando se exponen como objetos COM. Por ejemplo, si define una clase base con un miembro y, a continuación, hereda la clase base en una clase derivada que se expone como un objeto COM, los clientes que usan la clase derivada en el objeto COM no podrán usar los miembros heredados. Solo se puede tener acceso a los miembros de clase base desde objetos COM como instancias de una clase base y, a continuación, solo si la clase base también se crea como un objeto COM.  
  
## <a name="overloaded-methods"></a>Métodos sobrecargados  
 Aunque puede crear métodos sobrecargados con Visual Basic, no son compatibles con COM. Cuando una clase que contiene métodos sobrecargados se expone como un objeto COM, se generan nuevos nombres de método para los métodos sobrecargados.  
  
 Por ejemplo, considere una clase que tiene dos sobrecargas del `Synch` método. Cuando la clase se expone como un objeto COM, los nuevos nombres de método generados podrían ser `Synch` y `Synch_2` .  
  
 El cambio de nombre puede producir dos problemas para los consumidores del objeto COM.  
  
1. Es posible que los clientes no esperen los nombres de método generados.  
  
2. Los nombres de método generados en la clase expuesta como un objeto COM pueden cambiar cuando se agregan nuevas sobrecargas a la clase o a su clase base. Esto puede producir problemas de control de versiones.  
  
 Para resolver ambos problemas, asigne a cada método un nombre único, en lugar de usar sobrecarga, al desarrollar objetos que se expondrán como objetos COM.  
  
## <a name="use-of-com-objects-through-interop-assemblies"></a><a name="vbconinteroperabilitymarshalinganchor4"></a>Uso de objetos COM mediante ensamblados de interoperabilidad  
 Los ensamblados de interoperabilidad se usan casi como si fueran reemplazos de código administrados para los objetos COM que representan. Sin embargo, dado que son contenedores y no objetos COM reales, existen algunas diferencias entre el uso de ensamblados de interoperabilidad y ensamblados estándar. Estas áreas de diferencia incluyen la exposición de las clases y los tipos de datos de los parámetros y los valores devueltos.  
  
## <a name="classes-exposed-as-both-interfaces-and-classes"></a><a name="vbconinteroperabilitymarshalinganchor5"></a>Clases que se exponen como interfaces y clases  
 A diferencia de las clases de los ensamblados estándar, las clases COM se exponen en ensamblados de interoperabilidad como una interfaz y una clase que representa la clase COM. El nombre de la interfaz es idéntico al de la clase COM. El nombre de la clase de interoperabilidad es el mismo que el de la clase COM original, pero con la palabra "class" anexada. Por ejemplo, supongamos que tiene un proyecto con una referencia a un ensamblado de interoperabilidad para un objeto COM. Si la clase COM se denomina `MyComClass` , IntelliSense y el examinador de objetos muestran una interfaz denominada `MyComClass` y una clase denominada `MyComClassClass` .  
  
## <a name="creating-instances-of-a-net-framework-class"></a><a name="vbconinteroperabilitymarshalinganchor6"></a>Crear instancias de una clase .NET Framework  
 Generalmente, se crea una instancia de una clase .NET Framework utilizando la `New` instrucción con un nombre de clase. Tener una clase COM representada por un ensamblado de interoperabilidad es el único caso en el que se puede utilizar la `New` instrucción con una interfaz. A menos que use la clase COM con una `Inherits` instrucción, puede usar la interfaz como lo haría con una clase. En el código siguiente se muestra cómo crear un `Command` objeto en un proyecto que tiene una referencia al objeto com de la biblioteca de Microsoft Objetos de datos ActiveX 2,8:  
  
 [!code-vb[VbVbalrInterop#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#20)]  
  
 Sin embargo, si usa la clase COM como base para una clase derivada, debe usar la clase de interoperabilidad que representa la clase COM, como en el código siguiente:  
  
 [!code-vb[VbVbalrInterop#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#21)]  
  
> [!NOTE]
> Los ensamblados de interoperabilidad implementan implícitamente interfaces que representan clases COM. No debe intentar usar la `Implements` instrucción para implementar estas interfaces o se producirá un error.  
  
## <a name="data-types-for-parameters-and-return-values"></a><a name="vbconinteroperabilitymarshalinganchor7"></a>Tipos de datos de parámetros y valores devueltos  
 A diferencia de los miembros de ensamblados estándar, los miembros de ensamblado de interoperabilidad pueden tener tipos de datos que difieren de los usados en la declaración del objeto original. Aunque los ensamblados de interoperabilidad convierten implícitamente los tipos COM en tipos de Common Language Runtime compatibles, debe prestar atención a los tipos de datos que se usan en ambos lados para evitar errores en tiempo de ejecución. Por ejemplo, en los objetos COM creados en Visual Basic 6,0 y versiones anteriores, los valores de tipo `Integer` suponen el .NET Framework tipo equivalente, `Short` . Se recomienda usar el Examinador de objetos para examinar las características de los miembros importados antes de usarlos.  
  
## <a name="module-level-com-methods"></a><a name="vbconinteroperabilitymarshalinganchor8"></a>Métodos COM de nivel de módulo  
 La mayoría de los objetos COM se utilizan creando una instancia de una clase COM mediante la `New` palabra clave y llamando a los métodos del objeto. Una excepción a esta regla implica objetos COM que contienen `AppObj` clases de o `GlobalMultiUse` com. Estas clases son similares a los métodos de nivel de módulo en Visual Basic clases .NET. Visual Basic 6,0 y versiones anteriores crean implícitamente instancias de estos objetos por primera vez que se llama a uno de sus métodos. Por ejemplo, en Visual Basic 6,0 puede Agregar una referencia a la biblioteca de objetos de Microsoft DAO 3,6 y llamar al `DBEngine` método sin crear primero una instancia:  
  
```vb  
Dim db As DAO.Database  
' Open the database.  
Set db = DBEngine.OpenDatabase("C:\nwind.mdb")  
' Use the database object.  
```  
  
 Visual Basic .NET requiere que siempre se creen instancias de objetos COM antes de poder usar sus métodos. Para usar estos métodos en Visual Basic, declare una variable de la clase deseada y use la palabra clave New para asignar el objeto a la variable de objeto. La `Shared` palabra clave se puede usar cuando se desea asegurarse de que solo se crea una instancia de la clase.  
  
 [!code-vb[VbVbalrInterop#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#23)]  
  
## <a name="unhandled-errors-in-event-handlers"></a><a name="vbconinteroperabilitymarshalinganchor9"></a>Errores no controlados en los controladores de eventos  
 Un problema común de interoperabilidad implica errores en los controladores de eventos que controlan los eventos generados por objetos COM. Estos errores se omiten a menos que compruebe específicamente si hay errores mediante `On Error` `Try...Catch...Finally` instrucciones o. Por ejemplo, el ejemplo siguiente es de un proyecto Visual Basic .NET que tiene una referencia al objeto COM de la biblioteca de Microsoft Objetos de datos ActiveX 2,8.  
  
 [!code-vb[VbVbalrInterop#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#24)]  
  
 Este ejemplo genera un error según lo esperado. Sin embargo, si intenta usar el mismo ejemplo sin el `Try...Catch...Finally` bloque, se omitirá el error como si utilizara la `OnError Resume Next` instrucción. Sin el control de errores, se produce un error en la división por cero de forma silenciosa. Dado que tales errores nunca generan errores de excepción no controlados, es importante usar algún tipo de control de excepciones en los controladores de eventos que controlan los eventos de los objetos COM.  
  
### <a name="understanding-com-interop-errors"></a>Descripción de los errores de interoperabilidad COM  
 Sin el control de errores, las llamadas de interoperabilidad a menudo generan errores que proporcionan poca información. Siempre que sea posible, utilice el control de errores estructurado para proporcionar más información acerca de los problemas cuando se producen. Esto puede ser especialmente útil al depurar aplicaciones. Por ejemplo:  
  
 [!code-vb[VbVbalrInterop#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#25)]  
  
 Puede encontrar información como la descripción del error, HRESULT y el origen de los errores COM mediante el examen del contenido del objeto de excepción.  
  
## <a name="activex-control-issues"></a><a name="vbconinteroperabilitymarshalinganchor10"></a>Problemas de controles ActiveX  
 La mayoría de los controles ActiveX que funcionan con Visual Basic 6,0 funcionan con Visual Basic .NET sin problemas. Las excepciones principales son los controles de contenedor o los controles que contienen visualmente otros controles. A continuación se indican algunos ejemplos de controles anteriores que no funcionan correctamente con Visual Studio:  
  
- Control de marco de Microsoft Forms 2,0  
  
- Control de flechas, también conocido como control de número  
  
- Control de pestaña Sheridan  
  
 Solo existen algunas soluciones alternativas para los problemas de control ActiveX no admitidos. Puede migrar los controles existentes a Visual Studio si es el propietario del código fuente original. De lo contrario, puede consultar a los proveedores de software para actualizarlos. Versiones de controles compatibles con NET para reemplazar controles ActiveX no compatibles.  
  
## <a name="passing-readonly-properties-of-controls-byref"></a><a name="vbconinteroperabilitymarshalinganchor11"></a>Pasar propiedades ReadOnly de controles ByRef  
 Visual Basic .NET genera a veces errores COM como, "error 0x800A017F CTL_E_SETNOTSUPPORTED", cuando se pasan `ReadOnly` propiedades de algunos controles ActiveX antiguos como `ByRef` parámetros a otros procedimientos. Las llamadas a procedimientos similares desde Visual Basic 6,0 no generan un error, y los parámetros se tratan como si se hubieran pasado por valor. El mensaje de error de Visual Basic .NET indica que está intentando cambiar una propiedad que no tiene un procedimiento de propiedad `Set` .  
  
 Si tiene acceso al procedimiento al que se llama, puede evitar este error si usa la `ByVal` palabra clave para declarar los parámetros que aceptan `ReadOnly` propiedades. Por ejemplo:  
  
 [!code-vb[VbVbalrInterop#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#26)]  
  
 Si no tiene acceso al código fuente para el procedimiento al que se llama, puede forzar que la propiedad se pase por valor agregando un conjunto adicional de corchetes alrededor del procedimiento que realiza la llamada. Por ejemplo, en un proyecto que tenga una referencia al objeto COM de la biblioteca de Microsoft Objetos de datos ActiveX 2,8, puede usar:  
  
 [!code-vb[VbVbalrInterop#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#27)]  
  
## <a name="deploying-assemblies-that-expose-interop"></a><a name="vbconinteroperabilitymarshalinganchor12"></a>Implementar ensamblados que exponen la interoperabilidad  
 La implementación de ensamblados que exponen interfaces COM presenta algunos desafíos únicos. Por ejemplo, un posible problema se produce cuando las aplicaciones independientes hacen referencia al mismo ensamblado COM. Esta situación es habitual cuando se instala una nueva versión de un ensamblado y otra aplicación sigue usando la versión anterior del ensamblado. Si desinstala un ensamblado que comparte un archivo DLL, puede hacer que no esté disponible de forma involuntaria para los demás ensamblados.  
  
 Para evitar este problema, debe instalar los ensamblados compartidos en la caché de ensamblados global (GAC) y utilizar un módulo CRT para el componente. Si no puede instalar la aplicación en la GAC, debe instalarse en CommonFilesFolder en un subdirectorio específico de la versión.  
  
 Los ensamblados que no se comparten se deben ubicar en paralelo en el directorio con la aplicación que realiza la llamada.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Interoperabilidad COM](index.md)
- [TlbImp.exe (Importador de la biblioteca de tipos)](../../../framework/tools/tlbimp-exe-type-library-importer.md)
- [Tlbexp.exe (Exportador de la biblioteca de tipos)](../../../framework/tools/tlbexp-exe-type-library-exporter.md)
- [Tutorial: Implementación de la herencia mediante objetos COM](walkthrough-implementing-inheritance-with-com-objects.md)
- [Inherits Statement](../../language-reference/statements/inherits-statement.md)
- [Caché global de ensamblados](../../../framework/app-domains/gac.md)
