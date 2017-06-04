---
title: "How to: Examine and Instantiate Generic Types with Reflection | Microsoft Docs"
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
  - "reflection, generic types"
  - "generics [.NET Framework], reflection"
ms.assetid: f93b03b0-1778-43fc-bc6d-35983d210e74
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 16
---
# How to: Examine and Instantiate Generic Types with Reflection
La información de tipos genéricos se obtiene de la misma manera que la información sobre otros tipos: examinando un objeto <xref:System.Type> que representa el tipo genérico.  La diferencia de principio es que un tipo genérico tiene una lista de objetos <xref:System.Type> que representan sus parámetros de tipo genérico.  El primer procedimiento de esta sección examina los tipos genéricos.  
  
 Puede crear un objeto <xref:System.Type> que representa un tipo construido enlazando los argumentos de tipo a los parámetros de tipo de una definición de tipo genérico.  Todo ello se explica en el segundo procedimiento.  
  
### Para examinar un tipo genérico y sus parámetros de tipo  
  
1.  Obtenga una instancia de <xref:System.Type> que represente el tipo genérico.  En el código siguiente, el tipo se obtiene utilizando el operador `typeof` de C\# \(`GetType` en Visual Basic, `typeid` en Visual C\+\+\).  Vea el tema de la clase <xref:System.Type> para conocer otras maneras de obtener un objeto <xref:System.Type>.  Tenga en cuenta que en el resto de este procedimiento, el tipo se contiene en un parámetro de método denominado `t`.  
  
     [!code-cpp[HowToGeneric#2](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#2)]
     [!code-csharp[HowToGeneric#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#2)]
     [!code-vb[HowToGeneric#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#2)]  
  
2.  Utilice la propiedad <xref:System.Type.IsGenericType%2A> para determinar si el tipo es genérico y utilice la propiedad <xref:System.Type.IsGenericTypeDefinition%2A> para determinar si el tipo es una definición de tipo genérico.  
  
     [!code-cpp[HowToGeneric#3](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#3)]
     [!code-csharp[HowToGeneric#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#3)]
     [!code-vb[HowToGeneric#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#3)]  
  
3.  Obtenga una matriz que contiene los argumentos de tipo genérico utilizando el método <xref:System.Type.GetGenericArguments%2A>.  
  
     [!code-cpp[HowToGeneric#4](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#4)]
     [!code-csharp[HowToGeneric#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#4)]
     [!code-vb[HowToGeneric#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#4)]  
  
4.  Para cada argumento de tipo, determine si se trata de un parámetro de tipo \(por ejemplo, en una definición de tipo genérico\) o un tipo especificado para un parámetro de tipo \(por ejemplo, en un tipo construido\), utilizando la propiedad <xref:System.Type.IsGenericParameter%2A>.  
  
     [!code-cpp[HowToGeneric#5](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#5)]
     [!code-csharp[HowToGeneric#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#5)]
     [!code-vb[HowToGeneric#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#5)]  
  
5.  En el sistema de tipos, una instancia de <xref:System.Type> representa un parámetro de tipo genérico, igual que ocurre con los tipos normales.  El código siguiente muestra el nombre y la posición de parámetro de un objeto <xref:System.Type> que representa un parámetro de tipo genérico.  La posición del parámetro es aquí información trivial; resulta de más interés cuando está examinando un parámetro de tipo que se ha utilizado como un argumento de tipo de otro tipo genérico.  
  
     [!code-cpp[HowToGeneric#6](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#6)]
     [!code-csharp[HowToGeneric#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#6)]
     [!code-vb[HowToGeneric#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#6)]  
  
6.  Determine la restricción de tipo base y las restricciones de interfaz de un parámetro de tipo genérico utilizando el método <xref:System.Type.GetGenericParameterConstraints%2A> para obtener todas las restricciones de una única matriz.  No se garantiza que las restricciones sigan ningún orden determinado.  
  
     [!code-cpp[HowToGeneric#7](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#7)]
     [!code-csharp[HowToGeneric#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#7)]
     [!code-vb[HowToGeneric#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#7)]  
  
7.  Utilice la propiedad <xref:System.Type.GenericParameterAttributes%2A> para detectar las restricciones especiales de un parámetro de tipo, como requerir que sea un tipo de referencia.  La propiedad también incluye valores que representan variación, que puede enmascarar como se muestra en el código siguiente.  
  
     [!code-cpp[HowToGeneric#8](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#8)]
     [!code-csharp[HowToGeneric#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#8)]
     [!code-vb[HowToGeneric#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#8)]  
  
8.  Los atributos de restricción especiales son marcadores, y el mismo marcador \(<xref:System.Reflection.GenericParameterAttributes?displayProperty=fullName>\) que no representa ninguna restricción especial tampoco representa ninguna covarianza o contravarianza.  Por consiguiente, para comprobar cualquiera de estas condiciones, es preciso utilizar la máscara adecuada.  En este caso, utilice <xref:System.Reflection.GenericParameterAttributes?displayProperty=fullName> para aislar los marcadores de restricción especiales.  
  
     [!code-cpp[HowToGeneric#9](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#9)]
     [!code-csharp[HowToGeneric#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#9)]
     [!code-vb[HowToGeneric#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#9)]  
  
## Construir una instancia de un tipo genérico  
 Un tipo genérico es como una plantilla.  No puede crear instancias del mismo a menos que especifique los tipos reales para sus parámetros de tipo genérico.  Hacerlo en tiempo de ejecución, utilizando la reflexión, requiere el método <xref:System.Type.MakeGenericType%2A>.  
  
#### Para construir una instancia de un tipo genérico  
  
1.  Obtiene un objeto <xref:System.Type> que representa el tipo genérico.  El código siguiente obtiene el tipo genérico <xref:System.Collections.Generic.Dictionary%602> de dos formas distintas: usando la sobrecarga de método <xref:System.Type.GetType%28System.String%29?displayProperty=fullName> con una cadena que describe el tipo y llamando al método <xref:System.Type.GetGenericTypeDefinition%2A> en el tipo construido `Dictionary\<String, Example>` \(`Dictionary(Of String, Example)` en Visual Basic\).  El método <xref:System.Type.MakeGenericType%2A> requiere una definición de tipo genérico.  
  
     [!code-cpp[HowToGeneric#10](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#10)]
     [!code-csharp[HowToGeneric#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#10)]
     [!code-vb[HowToGeneric#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#10)]  
  
2.  Construya una matriz de argumentos de tipo que sustituir para los parámetros de tipo.  La matriz debe contener el número correcto de objetos <xref:System.Type>, en el mismo orden en que aparecen en la lista de parámetros de tipo.  En este caso, la clave \(el primer parámetro de tipo\) es del tipo <xref:System.String> y los valores incluidos en el diccionario son instancias de una clase denominada `Example`.  
  
     [!code-cpp[HowToGeneric#11](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#11)]
     [!code-csharp[HowToGeneric#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#11)]
     [!code-vb[HowToGeneric#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#11)]  
  
3.  Llame al método <xref:System.Type.MakeGenericType%2A> para enlazar los argumentos de tipo a los parámetros de tipo y construir el tipo.  
  
     [!code-cpp[HowToGeneric#12](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#12)]
     [!code-csharp[HowToGeneric#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#12)]
     [!code-vb[HowToGeneric#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#12)]  
  
4.  Utilice la sobrecarga de método <xref:System.Activator.CreateInstance%28System.Type%29> para crear un objeto del tipo construido.  El código siguiente almacena dos instancias de la clase `Example` en el objeto `Dictionary<String, Example>` resultante.  
  
     [!code-cpp[HowToGeneric#13](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#13)]
     [!code-csharp[HowToGeneric#13](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#13)]
     [!code-vb[HowToGeneric#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#13)]  
  
## Ejemplo  
 El ejemplo de código siguiente define un método `DisplayGenericType` para examinar las definiciones de tipos genéricos y los tipos construidos usados en el código y mostrar su información.  El método `DisplayGenericType` muestra cómo utilizar las propiedades <xref:System.Type.IsGenericType%2A>, <xref:System.Type.IsGenericParameter%2A> y <xref:System.Type.GenericParameterPosition%2A>, y el método <xref:System.Type.GetGenericArguments%2A>.  
  
 El ejemplo también define un método `DisplayGenericParameter` para examinar un parámetro de tipo genérico y mostrar sus restricciones.  
  
 El ejemplo de código define un conjunto de tipos de prueba, incluido un tipo genérico que ilustra las restricciones de parámetros de tipo, y muestra cómo mostrar información sobre estos tipos.  
  
 El ejemplo construye un tipo a partir de la clase <xref:System.Collections.Generic.Dictionary%602> creando una matriz de argumentos de tipo y llamando al método <xref:System.Type.MakeGenericType%2A>.  El programa compara el objeto <xref:System.Type> construido utilizando <xref:System.Type.MakeGenericType%2A> con un objeto <xref:System.Type> obtenido mediante `typeof` \(`GetType` en Visual Basic\), para demostrar que son iguales.  De forma parecida, el programa utiliza el método <xref:System.Type.GetGenericTypeDefinition%2A> para obtener la definición de tipo genérico del tipo construido y lo compara con el objeto <xref:System.Type> que representa la clase <xref:System.Collections.Generic.Dictionary%602>.  
  
 [!code-cpp[HowToGeneric#1](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#1)]
 [!code-csharp[HowToGeneric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#1)]
 [!code-vb[HowToGeneric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#1)]  
  
## Compilar el código  
  
-   El código contiene las instrucciones `using` de C\# \(`Imports` en Visual Basic\) necesarias para la compilación.  
  
-   No se requiere ninguna referencia de ensamblado adicional.  
  
-   Compile el código de la línea de comandos mediante csc.exe, vbc.exe, o cl.exe.  Para compilar el código en Visual Studio, póngalo en una plantilla de proyecto de aplicación de consola.  
  
## Vea también  
 <xref:System.Type>   
 <xref:System.Reflection.MethodInfo>   
 [Reflection and Generic Types](../../../docs/framework/reflection-and-codedom/reflection-and-generic-types.md)   
 [Viewing Type Information](../../../docs/framework/reflection-and-codedom/viewing-type-information.md)   
 [Genéricos](../../../docs/standard/generics/index.md)