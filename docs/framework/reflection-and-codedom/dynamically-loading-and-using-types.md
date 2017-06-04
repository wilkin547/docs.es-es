---
title: "Dynamically Loading and Using Types | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "late binding, about late binding"
  - "early binding"
  - "dynamically loading and using types"
  - "implicit late binding"
  - "reflection, dynamically using types"
ms.assetid: db985bec-5942-40ec-b13a-771ae98623dc
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# Dynamically Loading and Using Types
La reflexión proporciona la infraestructura que utilizan los compiladores de lenguaje, como [!INCLUDE[vbprvbext](../../../includes/vbprvbext-md.md)] y JScript, para implementar el enlace implícito en tiempo de ejecución.  El enlace es el proceso de buscar la declaración \(es decir, la implementación\) que corresponde a un tipo especificado de manera exclusiva.  Cuando este proceso se produce en tiempo de ejecución en lugar de en tiempo de compilación, se denomina enlace en tiempo de ejecución.  [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] permite utilizar en el código el enlace implícito en tiempo de ejecución; el compilador de Visual Basic llama a un método auxiliar que utiliza la reflexión para obtener el tipo del objeto.  Los argumentos que se pasan al método auxiliar hacen que se invoque el método apropiado en tiempo de ejecución.  Dichos argumentos son la instancia \(un objeto\) en la que se va a invocar al método, al nombre del método invocado \(una cadena\) y a los argumentos pasados al método invocado \(una matriz de objetos\).  
  
 En el ejemplo siguiente, el compilador de Visual Basic utiliza implícitamente la reflexión para llamar a un método en un objeto cuyo tipo se desconoce en tiempo de compilación.  Una clase **HelloWorld** tiene un método **PrintHello** que imprime "Hello World" de forma concatenada con texto que se pasa al método **PrintHello**.  El método **PrintHello** al que se llama en este ejemplo es en realidad un método <xref:System.Type.InvokeMember%2A?displayProperty=fullName>; el código de Visual Basic permite la invocación del método **PrintHello** como si se conociese el tipo del objeto \(helloObj\) en tiempo de compilación \(enlace en tiempo de compilación\) y no en tiempo de ejecución \(enlace en tiempo de ejecución\).  
  
```  
Imports System  
Module Hello  
    Sub Main()  
        ' Sets up the variable.  
        Dim helloObj As Object  
        ' Creates the object.  
        helloObj = new HelloWorld()  
        ' Invokes the print method as if it was early bound  
        ' even though it is really late bound.  
        helloObj.PrintHello("Visual Basic Late Bound")  
    End Sub  
End Module  
```  
  
## Enlace personalizado  
 Además de utilizarla implícitamente los compiladores para el enlace en tiempo de ejecución, la reflexión puede utilizarse explícitamente en código para realizar el enlace en tiempo de ejecución.  
  
 [Common Language Runtime](../../../docs/standard/clr.md) admite diversos lenguajes de programación y las reglas de enlace de dichos lenguajes varían.  En el caso del enlace en tiempo de compilación, los generadores de código pueden controlar completamente este enlace.  Sin embargo, en el caso del enlace en tiempo de ejecución mediante reflexión, se ha de controlar el enlace mediante enlace personalizado.  La clase <xref:System.Reflection.Binder> proporciona un control personalizado de selección e invocación de miembros.  
  
 Mediante el enlace personalizado se puede cargar un ensamblado en tiempo de ejecución, obtener información sobre los tipos de dicho ensamblado, especificar el tipo que se desea y, a continuación, invocar a métodos u obtener acceso a campos o propiedades de dicho tipo.  Esta técnica resulta útil si se desconoce el tipo de un objeto en tiempo de compilación, como cuando el tipo de objeto depende de los datos proporcionados por el usuario.  
  
 En el ejemplo siguiente se muestra un enlazador simple personalizado que no proporciona ninguna conversión de tipo de argumento.  El código para `Simple_Type.dll` va antes del ejemplo principal.  Asegúrese de que crea `Simple_Type.dll` y de que incluye, a continuación, una referencia a este enlazador en el proyecto en tiempo de compilación.  
  
 [!code-cpp[Conceptual.Types.Dynamic#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.dynamic/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.Types.Dynamic#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.dynamic/cs/source1.cs#1)]
 [!code-vb[Conceptual.Types.Dynamic#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.dynamic/vb/source1.vb#1)]  
  
### InvokeMember y CreateInstance  
 Utilice <xref:System.Type.InvokeMember%2A?displayProperty=fullName> para invocar un miembro de un tipo.  Los métodos **CreateInstance** de varias clases, como [System.Activator](frlrfSystemActivatorClassCreateInstanceTopic) y [System.Reflection.Assembly](frlrfSystemReflectionAssemblyClassCreateInstanceTopic), son formas especializadas de **InvokeMember** que crean nuevas instancias del tipo especificado.  La clase **Binder** se utiliza para la resolución de sobrecarga y la conversión de argumentos en estos métodos.  
  
 En el ejemplo siguiente se muestran las tres posibles combinaciones de conversión de argumentos \(conversión de tipos\) y selección de miembros.  En el primer caso \(Case 1\), no se precisa ninguna conversión de argumentos o selección de miembros.  En el segundo caso \(Case 2\), sólo se precisa la selección de miembros.  En el tercer caso \(Case 3\), sólo se precisa la conversión de argumentos.  
  
 [!code-cpp[Conceptual.Types.Dynamic#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.dynamic/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.Types.Dynamic#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.dynamic/cs/source2.cs#2)]
 [!code-vb[Conceptual.Types.Dynamic#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.dynamic/vb/source2.vb#2)]  
  
 Se precisa la resolución de sobrecarga cuando hay más de un miembro con el mismo nombre.  Los métodos <xref:System.Reflection.Binder.BindToMethod%2A?displayProperty=fullName> y <xref:System.Reflection.Binder.BindToField%2A?displayProperty=fullName> se utilizan para resolver el enlace en un solo miembro.  **Binder.BindToMethod** también proporciona resolución de propiedades mediante los descriptores de acceso de propiedades **get** y **set**.  
  
 **BindToMethod** devuelve la clase <xref:System.Reflection.MethodBase> que se va a invocar o una referencia nula \(**Nothing** en Visual Basic\) si la invocación no es posible.  El valor devuelto de **MethodBase** no tiene que ser uno de los valores que contiene el parámetro *match*, si bien suele ser el caso.  
  
 Cuando hay argumentos ByRef, es posible que el llamador desee que se le devuelvan.  Por tanto, **Binder** permite a un cliente asignar de nuevo la matriz de argumentos a su formulario original si **BindToMethod** ha manipulado la matriz de argumentos.  Para ello, es preciso garantizar al llamador que no se modifica el orden de los argumentos.  Cuando se pasan argumentos por nombre, **Binder** reorganiza la matriz de argumentos y eso es lo que ve el llamador.  Para obtener más información, vea <xref:System.Reflection.Binder.ReorderArgumentArray%2A?displayProperty=fullName>.  
  
 El conjunto de miembros disponibles son los miembros definidos en el tipo o cualquier tipo base.  Si se especifica [BindingFlags.NonPublic](frlrfSystemReflectionBindingFlagsClassTopic), se devolverán los miembros de cualquier accesibilidad del conjunto.  Si no se especifica **BindingFlags.NonPublic**, el enlazador deberá imponer las reglas de accesibilidad.  Cuando se especifica el marcador de enlace **Public** o **NonPublic**, también se debe especificar el marcador de enlace **Instance** o **Static**; en caso contrario, no se devolverá ningún miembro.  
  
 Si sólo hay un miembro con el nombre especificado, no es necesaria la devolución de llamada y el enlace se realiza en dicho método.  En el primer caso \(Case 1\) del ejemplo de código se ilustra este punto: hay sólo un método **PrintBob** disponible, por lo que no es necesario devolver la llamada.  
  
 Si hay más de un miembro en el conjunto disponible, todos estos métodos se pasan a **BindToMethod**, que selecciona el método apropiado y lo devuelve.  En el segundo caso \(Case 2\) del ejemplo de código, hay dos métodos denominados **PrintValue**.  El método apropiado se selecciona al llamar a **BindToMethod**.  
  
 <xref:System.Reflection.Binder.ChangeType%2A> lleva a cabo una conversión de argumentos \(conversión de tipos\), y convierte los argumentos reales al tipo de los argumentos formales del método seleccionado.  Se llama a **ChangeType** para cada argumento, incluso si los tipos son exactamente iguales.  
  
 En el tercer caso \(Case 3\) del ejemplo de código, se pasa un argumento real de tipo **String** con un valor de "5.5" a un método con un argumento formal de tipo **Double**.  Para que la invocación se realice correctamente, el valor de cadena "5.5" debe convertirse a un valor de tipo double.  **ChangeType** lleva a cabo esta conversión.  
  
 **ChangeType** realiza sólo [conversiones de ampliación](../../../docs/standard/base-types/type-conversion.md) o sin pérdidas, tal como se muestra en la siguiente tabla.  
  
|Tipo de origen|Tipo de destino|  
|--------------------|---------------------|  
|Cualquier tipo|El tipo base correspondiente|  
|Cualquier tipo|Interfaz que implementa|  
|Char|UInt16, UInt32, Int32, UInt64, Int64, Single, Double|  
|Byte|Char, UInt16, Int16, UInt32, Int32, UInt64, Int64, Single, Double|  
|SByte|Int16, Int32, Int64, Single, Double|  
|UInt16|UInt32, Int32, UInt64, Int64, Single, Double|  
|Int16|Int32, Int64, Single, Double|  
|UInt32|UInt64, Int64, Single, Double|  
|Int32|Int64, Single, Double|  
|UInt64|Single, Double|  
|Int64|Single, Double|  
|Single|Double|  
|Tipo de no referencia|Tipo de referencia|  
  
 La clase <xref:System.Type> tiene métodos **Get** que utilizan parámetros de tipo **Binder** para resolver las referencias a un miembro determinado.  <xref:System.Type.GetConstructor%2A?displayProperty=fullName>, <xref:System.Type.GetMethod%2A?displayProperty=fullName> y <xref:System.Type.GetProperty%2A?displayProperty=fullName> buscan un miembro determinado del tipo actual; para ello, proporcionan información de la firma de dicho miembro.  Se devuelve la llamada a <xref:System.Reflection.Binder.SelectMethod%2A?displayProperty=fullName> y <xref:System.Reflection.Binder.SelectProperty%2A?displayProperty=fullName> para seleccionar la información de firma especificada de los métodos correspondientes.  
  
## Vea también  
 <xref:System.Type.InvokeMember%2A?displayProperty=fullName>   
 <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>   
 [Viewing Type Information](../../../docs/framework/reflection-and-codedom/viewing-type-information.md)   
 [Conversión de tipos en .NET Framework](../../../docs/standard/base-types/type-conversion.md)