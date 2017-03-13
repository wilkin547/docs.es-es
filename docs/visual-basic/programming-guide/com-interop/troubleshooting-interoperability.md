---
title: "Solucionar problemas de interoperabilidad (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "ensamblados [Visual Basic]"
  - "ensamblados [Visual Basic], implementar"
  - "interoperabilidad COM, solucionar problemas"
  - "objetos COM, solucionar problemas"
  - "ensamblados de interoperabilidad"
  - "interoperabilidad, implementar ensamblados"
  - "interoperabilidad, instalar ensamblados que compartan componentes"
  - "interoperabilidad, compartir componentes"
  - "interoperabilidad, compartir componentes"
  - "interoperabilidad, solucionar problemas"
  - "componentes compartidos, utilizar con ensamblados"
  - "solucionar problemas de interoperabilidad"
  - "solucionar problemas de Visual Basic, interoperabilidad"
ms.assetid: b324cc1e-b03c-4f39-aea6-6a6d5bfd0e37
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 21
---
# Solucionar problemas de interoperabilidad (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Al interoperar entre COM y el código administrado de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)], es posible que encuentre alguno de los siguientes problemas comunes.  
  
##  <a name="vbconinteroperabilitymarshalinganchor1"></a> Cálculo de referencias de interoperabilidad  
 En ocasiones es posible que necesite usar tipos de datos que no forman parte de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)].  Los ensamblados de interoperabilidad controlan la mayor parte del trabajo para los objetos COM, pero es posible que tenga que controlar los tipos de datos usados cuando exponga objetos administrados a COM.  Por ejemplo, las estructuras de las bibliotecas de clases deben especificar el tipo no administrado `BStr` en las cadenas enviadas a los objetos COM creados con Visual Basic 6.0 y versiones anteriores.  En estos casos, puede utilizar el atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> para exponer los tipos administrados como tipos no administrados.  
  
##  <a name="vbconinteroperabilitymarshalinganchor2"></a> Exportar cadenas de longitud fija a código no administrado  
 En Visual Basic 6.0 y versiones anteriores, las cadenas se exportan a objetos COM como secuencias de bytes sin un carácter de terminación de tipo NULL.  Por compatibilidad con otros lenguajes, [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong-md.md)] incluye un carácter de terminación al exportar cadenas.  La mejor forma de solucionar esta incompatibilidad es exportar las cadenas sin carácter de terminación como matrices de tipo `Byte` o `Char`.  
  
##  <a name="vbconinteroperabilitymarshalinganchor3"></a> Exportar jerarquías de herencia  
 Las jerarquías de clases administradas desaparecen cuando las clases se exponen como objetos COM.  Por ejemplo, si define una clase base con un miembro y después hereda la clase base en una clase derivada expuesta como un objeto COM, los clientes que utilizan la clase derivada en el objeto COM no podrán utilizar los miembros heredados.  Sólo se tiene acceso a los miembros de la clase base desde los objetos COM como instancias de una clase base y sólo en el caso de que la clase base también se cree como un objeto COM.  
  
## Métodos sobrecargados  
 Aunque se pueden crear métodos sobrecargados con [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)], COM no los admite.  Cuando una clase que contiene métodos sobrecargados se expone como objeto COM, se generan nombres de método nuevos para los métodos sobrecargados.  
  
 Suponga, por ejemplo, que una clase tiene dos sobrecargas del método `Synch`.  Si la clase se expone como objeto COM, los nombres de método nuevos generados podrían ser `Synch` y `Synch_2`.  
  
 El cambio de nombre puede producir dos problemas para los consumidores del objeto COM.  
  
1.  Es posible que los clientes no esperen los nombres de método generados.  
  
2.  Los nombres de método generados en la clase expuesta como objeto COM pueden cambiar al agregar nuevas sobrecargas a la clase o a su clase base.  Esto puede provocar problemas de versiones.  
  
 Para resolver ambos problemas, asigne un nombre único a cada método, en lugar de usar la sobrecarga, cuando desarrolle objetos que se van a exponer como objetos COM.  
  
##  <a name="vbconinteroperabilitymarshalinganchor4"></a> Uso de objetos COM mediante ensamblados de interoperabilidad  
 Los ensamblados de interoperabilidad se usan casi como si fueran equivalentes de código administrado para los objetos COM que representan.  Sin embargo, como son contenedores y no objetos COM reales, hay algunas diferencias entre el uso de ensamblados de interoperabilidad y ensamblados estándar.  Son diferencias en la exposición de clases y los tipos de datos para parámetros y valores devueltos.  
  
##  <a name="vbconinteroperabilitymarshalinganchor5"></a> Clases expuestas como interfaces y como clases  
 A diferencia de las clases de los ensamblados estándar, las clases COM se exponen en ensamblados de interoperabilidad como una interfaz y una clase que representa la clase COM.  El nombre de la interfaz es idéntico al de la clase COM.  El nombre de la clase de interoperabilidad es igual al de la clase COM original, pero con la palabra "Class" anexada.  Por ejemplo, suponga que tiene un proyecto con una referencia a un ensamblado de interoperabilidad para un objeto COM.  Si la clase COM se denomina `MyComClass`, IntelliSense y el Examinador de objetos muestran una interfaz denominada `MyComClass` y una clase denominada `MyComClassClass`.  
  
##  <a name="vbconinteroperabilitymarshalinganchor6"></a> Crear instancias de una clase de .NET Framework  
 Por lo general, una instancia de una clase de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] se crea mediante la instrucción `New` con un nombre de clase.  La representación de una clase COM mediante un ensamblado de interoperabilidad es el caso en el que se puede utilizar la instrucción `New` con una interfaz.  A menos que use la clase COM con una instrucción `Inherits`, puede utilizar la interfaz del mismo modo que usaría una clase.  En el código siguiente se muestra cómo se crea un objeto `Command` en un proyecto que tiene una referencia al objeto COM de Microsoft ActiveX Data Objects 2.8 Library:  
  
 [!code-vb[VbVbalrInterop#20](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_1.vb)]  
  
 Sin embargo, si utiliza la clase COM como base para una clase derivada deberá utilizar la clase de interoperabilidad que representa la clase COM, como en las líneas siguientes:  
  
 [!code-vb[VbVbalrInterop#21](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_2.vb)]  
  
> [!NOTE]
>  Los ensamblados de interoperabilidad implementan implícitamente interfaces que representan clases COM.  No debe intentar usar la instrucción `Implements` para implementar estas interfaces; si lo hace, se producirá un error.  
  
##  <a name="vbconinteroperabilitymarshalinganchor7"></a> Tipos de datos para parámetros y valores devueltos  
 A diferencia de los miembros de los ensamblados estándar, los miembros de los ensamblados de interoperabilidad pueden tener tipos de datos distintos de los usados en la declaración original del objeto.  Aunque los ensamblados de interoperabilidad convierten implícitamente los tipos COM en tipos compatibles con Common Language Runtime, debe tener en cuenta los tipos que se usan en los dos lados para evitar errores en tiempo de ejecución.  Por ejemplo, en los objetos COM creados con Visual Basic 6.0 y versiones anteriores, los valores de tipo `Integer` adquieren el tipo de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] equivalente, `Short`.  Se recomienda usar el Examinador de objetos para examinar las características de los miembros importados antes de usarlos.  
  
##  <a name="vbconinteroperabilitymarshalinganchor8"></a> Métodos COM de módulos  
 La mayoría de los objetos COM se utilizan creando una instancia de una clase COM mediante la palabra clave `New` y, a continuación, llamando a métodos del objeto.  Existe una excepción a esta regla relacionada con los objetos COM que contienen clases COM `AppObj` o `GlobalMultiUse`.  Estas clases son similares a los métodos de nivel de módulo de las clases de [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong-md.md)].  Visual Basic 6.0 y versiones anteriores crean implícitamente instancias de estos objetos la primera vez que se llama a uno de sus métodos.  Por ejemplo, en Visual Basic 6.0 es posible agregar una referencia a Microsoft DAO 3.6 Object Library y llamar al método `DBEngine` sin crear primero una instancia:  
  
```  
Dim db As DAO.Database  
' Open the database.  
Set db = DBEngine.OpenDatabase("C:\nwind.mdb")  
' Use the database object.  
```  
  
 [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong-md.md)] requiere que siempre se creen instancias de los objetos COM antes de usar sus métodos.  Para utilizar estos métodos en [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong-md.md)], declare una variable de la clase que desee y use la nueva palabra clave para asignar el objeto a la variable de objeto.  Puede utilizar la palabra clave `Shared` para asegurarse de que sólo se crea una instancia de la clase.  
  
 [!code-vb[VbVbalrInterop#23](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_3.vb)]  
  
##  <a name="vbconinteroperabilitymarshalinganchor9"></a> Errores no controlados en controladores de errores  
 Un problema habitual de interoperabilidad implica a los errores de controladores de eventos que controlan eventos producidos por objetos COM.  Estos errores se omiten a menos que se compruebe específicamente la existencia de errores mediante instrucciones `On Error` o `Try...Catch...Finally`.  Por ejemplo, el ejemplo siguiente procede de un proyecto de [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong-md.md)] que tiene una referencia al objeto COM de Microsoft ActiveX Data Objects 2.8 Library.  
  
 [!code-vb[VbVbalrInterop#24](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_4.vb)]  
  
 Este ejemplo produce un error, según lo esperado.  Sin embargo, si intenta ejecutar el mismo ejemplo sin el bloque `Try...Catch...Finally`, el error se omitirá como si hubiera utilizado la instrucción `OnError Resume Next`.  Sin control de errores, la división por cero produce un error pero no lo comunica.  Dado que tales errores nunca producen errores de excepción no controlada, es importante usar algún tipo de control de excepciones en los controladores de eventos que controlan los eventos de objetos COM.  
  
### Errores de interoperabilidad COM  
 Sin control de errores, las llamadas de interoperabilidad suelen generar errores que proporcionan poca información.  Siempre que sea posible, utilice control de errores estructurado para proporcionar más información sobre los errores en el momento en que se produzcan.  Esto puede ser especialmente útil al depurar las aplicaciones.  Por ejemplo:  
  
 [!code-vb[VbVbalrInterop#25](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_5.vb)]  
  
 Puede examinar el contenido del objeto de excepción para averiguar información tal como la descripción del error, HRESULT y el origen de los errores COM.  
  
##  <a name="vbconinteroperabilitymarshalinganchor10"></a> Cuestiones sobre controles ActiveX  
 La mayor parte de los controles ActiveX que funcionan con Visual Basic 6.0 funcionan con [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong-md.md)] sin problemas.  Las principales excepciones son los controles contenedores, o controles que contienen visualmente a otros controles.  Estos son algunos ejemplos de controles más antiguos que no funcionan correctamente con [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)]:  
  
-   Control Microsoft Forms 2.0 Frame  
  
-   Control Arriba\-Abajo, también conocido como control giratorio  
  
-   Control Tab Sheridan  
  
 Sólo hay unas pocas soluciones para los problemas de controles ActiveX incompatibles.  Es posible migrar los controles existentes a [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] si se dispone del código fuente original.  Si no es así, puede consultar a los proveedores de software para ver si disponen de versiones actualizadas de los controles compatibles con .NET para sustituir los controles ActiveX incompatibles.  
  
##  <a name="vbconinteroperabilitymarshalinganchor11"></a> Pasar propiedades ReadOnly de controles ByRef  
 [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong-md.md)] produce a veces errores COM como "Error 0x800A017F CTL\_E\_SETNOTSUPPORTED" cuando se pasan propiedades `ReadOnly` de algunos controles ActiveX antiguos como parámetros `ByRef` a otros procedimientos.  Las llamadas de procedimiento similares desde Visual Basic 6.0 no producen ningún error; los parámetros se tratan como si se hubieran pasado por valor.  El mensaje de error que aparece en [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong-md.md)] es el objeto COM que informa de que se está intentando cambiar una propiedad que no tiene un procedimiento `Set` de propiedad.  
  
 Si tiene acceso al procedimiento al que se está llamando, puede utiliza la palabra clave `ByVal` para declarar parámetros que acepten propiedades `ReadOnly` y, así, evitar el error.  Por ejemplo:  
  
 [!code-vb[VbVbalrInterop#26](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_6.vb)]  
  
 Si no tiene acceso al código fuente de la propiedad a la que se está llamando puede forzar que se pase la propiedad por valor; para ello, agregue un conjunto adicional de llaves alrededor del procedimiento que hace la llamada.  Por ejemplo, en un proyecto que tenga una referencia al objeto COM de Microsoft ActiveX Data Objects 2.8 Library, se puede utilizar:  
  
 [!code-vb[VbVbalrInterop#27](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_7.vb)]  
  
##  <a name="vbconinteroperabilitymarshalinganchor12"></a> Implementar ensamblados que expongan interoperabilidad  
 Implementar ensamblados que expongan interfaces COM supone algunas dificultades.  Por ejemplo, se produce un posible problema si aplicaciones independientes hacen referencia al mismo ensamblado COM.  Es una situación normal cuando se instala una nueva versión de un ensamblado habiendo otra aplicación que utiliza aún la versión antigua de ese ensamblado.  Si desinstala cualquier ensamblado que comparta un archivo DLL, puede impedir que se disponga de él en otros ensamblados sin desearlo.  
  
 Para evitarlo, debe instalar ensamblados compartidos en la caché global de ensamblados \(GAC\) y que el componente utilice un MergeModule.  Si no puede instalar la aplicación en la GAC, debe instalarla en CommonFilesFolder en un subdirectorio específico para esa versión.  
  
 Los ensamblados no compartidos deben instalarse en el directorio en paralelo con la aplicación de llamada.  
  
## Vea también  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Interoperabilidad COM](../../../visual-basic/programming-guide/com-interop/index.md)   
 [Tlbimp.exe \(Type Library Importer\)](../Topic/Tlbimp.exe%20\(Type%20Library%20Importer\).md)   
 [Tlbexp.exe \(Type Library Exporter\)](../Topic/Tlbexp.exe%20\(Type%20Library%20Exporter\).md)   
 [Tutorial: Implementar la herencia mediante objetos COM](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)   
 [Inherits \(Instrucción\)](../../../visual-basic/language-reference/statements/inherits-statement.md)   
 [Caché global de ensamblados](../Topic/Global%20Assembly%20Cache.md)