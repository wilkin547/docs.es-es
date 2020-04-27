---
title: Procedimiento para examinar y crear instancias de tipos genéricos mediante la reflexión
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- reflection, generic types
- generics [.NET Framework], reflection
ms.assetid: f93b03b0-1778-43fc-bc6d-35983d210e74
ms.openlocfilehash: 62e4e066740d0422f8f7045b043a5725278c209c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130131"
---
# <a name="how-to-examine-and-instantiate-generic-types-with-reflection"></a>Procedimiento para examinar y crear instancias de tipos genéricos mediante la reflexión
La información sobre los tipos genéricos se obtiene de la misma manera que la información sobre otros tipos: mediante el examen de un objeto <xref:System.Type> que representa el tipo genérico. La diferencia principal es que un tipo genérico tiene una lista de objetos <xref:System.Type> que representan sus parámetros de tipo genérico. En el primer procedimiento de esta sección se examinan tipos genéricos.  
  
 Puede crear un objeto <xref:System.Type> que representa un tipo construido. Para ello, se enlazan los argumentos de tipo a los parámetros de tipo de una definición de tipo genérico. En el segundo procedimiento se muestra cómo hacerlo.  
  
### <a name="to-examine-a-generic-type-and-its-type-parameters"></a>Para examinar un tipo genérico y sus parámetros de tipo  
  
1. Obtenga una instancia de <xref:System.Type> que representa el tipo genérico. En el código siguiente, el tipo se obtiene con el operador de C# `typeof` (`GetType` en Visual Basic y `typeid` en Visual C++). Vea el tema de la clase <xref:System.Type> para conocer otras formas de obtener un objeto <xref:System.Type>. Tenga en cuenta que en el resto de este procedimiento, el tipo está incluido en un parámetro de método denominado `t`.  
  
     [!code-cpp[HowToGeneric#2](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#2)]
     [!code-csharp[HowToGeneric#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#2)]
     [!code-vb[HowToGeneric#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#2)]  
  
2. Use la propiedad <xref:System.Type.IsGenericType%2A> para determinar si el tipo es genérico y la propiedad <xref:System.Type.IsGenericTypeDefinition%2A> para determinar si el tipo es una definición de tipo genérico.  
  
     [!code-cpp[HowToGeneric#3](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#3)]
     [!code-csharp[HowToGeneric#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#3)]
     [!code-vb[HowToGeneric#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#3)]  
  
3. Obtenga una matriz que contiene los argumentos de tipo genérico con el método <xref:System.Type.GetGenericArguments%2A>.  
  
     [!code-cpp[HowToGeneric#4](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#4)]
     [!code-csharp[HowToGeneric#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#4)]
     [!code-vb[HowToGeneric#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#4)]  
  
4. Para cada argumento de tipo, determine si es un parámetro de tipo (por ejemplo, en una definición de tipo genérico) o un tipo que se ha especificado para un parámetro de tipo (por ejemplo, en un tipo construido) mediante la propiedad <xref:System.Type.IsGenericParameter%2A>.  
  
     [!code-cpp[HowToGeneric#5](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#5)]
     [!code-csharp[HowToGeneric#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#5)]
     [!code-vb[HowToGeneric#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#5)]  
  
5. En el sistema de tipos, un parámetro de tipo genérico se representa mediante una instancia de <xref:System.Type>, igual que los tipos normales. El siguiente código muestra el nombre y la posición del parámetro de un objeto <xref:System.Type> que representa un parámetro de tipo genérico. La posición del parámetro es información trivial en este caso; resulta más interesante al examinar un parámetro de tipo que se ha usado como un argumento de tipo de otro tipo genérico.  
  
     [!code-cpp[HowToGeneric#6](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#6)]
     [!code-csharp[HowToGeneric#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#6)]
     [!code-vb[HowToGeneric#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#6)]  
  
6. Use el método <xref:System.Type.GetGenericParameterConstraints%2A> para obtener todas las restricciones de una sola matriz y determinar la restricción de tipo base y las restricciones de interfaz de un parámetro de tipo genérico. No se garantiza que las restricciones estén en un orden determinado.  
  
     [!code-cpp[HowToGeneric#7](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#7)]
     [!code-csharp[HowToGeneric#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#7)]
     [!code-vb[HowToGeneric#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#7)]  
  
7. Use la propiedad <xref:System.Type.GenericParameterAttributes%2A> para detectar las restricciones especiales de un parámetro de tipo, como la exigencia de que sea un tipo de referencia. La propiedad también incluye valores que representan la varianza, que se puede enmascarar como se muestra en el código siguiente.  
  
     [!code-cpp[HowToGeneric#8](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#8)]
     [!code-csharp[HowToGeneric#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#8)]
     [!code-vb[HowToGeneric#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#8)]  
  
8. Los atributos de las restricciones especiales son marcas; la misma marca (<xref:System.Reflection.GenericParameterAttributes.None?displayProperty=nameWithType>) que no representa ninguna restricción especial no representa tampoco ninguna covarianza ni contravarianza. Por lo tanto, para probar cualquiera de estas condiciones, debe usar la máscara apropiada. En este caso, use <xref:System.Reflection.GenericParameterAttributes.SpecialConstraintMask?displayProperty=nameWithType> para aislar las marcas de restricciones especiales.  
  
     [!code-cpp[HowToGeneric#9](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#9)]
     [!code-csharp[HowToGeneric#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#9)]
     [!code-vb[HowToGeneric#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#9)]  
  
## <a name="constructing-an-instance-of-a-generic-type"></a>Creación de una instancia de un tipo genérico  
 Un tipo genérico es como una plantilla. No se pueden crear instancias de él, a menos que se especifiquen tipos reales para sus parámetros de tipo genérico. Para hacerlo en tiempo de ejecución con la reflexión, se necesita el método <xref:System.Type.MakeGenericType%2A>.  
  
#### <a name="to-construct-an-instance-of-a-generic-type"></a>Para crear una instancia de un tipo genérico  
  
1. Obtenga un objeto <xref:System.Type> que representa el tipo genérico. El código siguiente obtiene el tipo genérico <xref:System.Collections.Generic.Dictionary%602> de dos maneras: mediante la sobrecarga del método <xref:System.Type.GetType%28System.String%29?displayProperty=nameWithType> con una cadena que describe el tipo y mediante la llamada al método <xref:System.Type.GetGenericTypeDefinition%2A> en el tipo construido `Dictionary\<String, Example>` (`Dictionary(Of String, Example)` en Visual Basic). El método <xref:System.Type.MakeGenericType%2A> exige una definición de tipo genérico.  
  
     [!code-cpp[HowToGeneric#10](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#10)]
     [!code-csharp[HowToGeneric#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#10)]
     [!code-vb[HowToGeneric#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#10)]  
  
2. Cree una matriz de argumentos de tipo para sustituir a los parámetros de tipo. La matriz debe contener el número correcto de objetos <xref:System.Type>, en el mismo orden en que aparecen en la lista de parámetros de tipo. En este caso, la clave (el primer parámetro de tipo) es de tipo <xref:System.String> y los valores del diccionario son instancias de una clase denominada `Example`.  
  
     [!code-cpp[HowToGeneric#11](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#11)]
     [!code-csharp[HowToGeneric#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#11)]
     [!code-vb[HowToGeneric#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#11)]  
  
3. Llame al método <xref:System.Type.MakeGenericType%2A> para enlazar los argumentos de tipo a los parámetros de tipo y crear el tipo.  
  
     [!code-cpp[HowToGeneric#12](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#12)]
     [!code-csharp[HowToGeneric#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#12)]
     [!code-vb[HowToGeneric#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#12)]  
  
4. Use la sobrecarga del método <xref:System.Activator.CreateInstance%28System.Type%29> para crear un objeto del tipo construido. El código siguiente almacena dos instancias de la clase `Example` en el objeto `Dictionary<String, Example>` resultante.  
  
     [!code-cpp[HowToGeneric#13](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#13)]
     [!code-csharp[HowToGeneric#13](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#13)]
     [!code-vb[HowToGeneric#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#13)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se define un método `DisplayGenericType` para examinar las definiciones de tipo genérico y los tipos construidos usados en el código y mostrar su información. El método `DisplayGenericType` muestra cómo usar las propiedades <xref:System.Type.IsGenericType%2A>, <xref:System.Type.IsGenericParameter%2A> y <xref:System.Type.GenericParameterPosition%2A>, y el método <xref:System.Type.GetGenericArguments%2A>.  
  
 En el ejemplo también se define un método `DisplayGenericParameter` para examinar un parámetro de tipo genérico y mostrar sus restricciones.  
  
 En el ejemplo de código se define un conjunto de tipos de prueba, incluido un tipo genérico que ilustra las restricciones de parámetro de tipo, y se muestra cómo visualizar información sobre estos tipos.  
  
 El ejemplo crea un tipo a partir de la clase <xref:System.Collections.Generic.Dictionary%602> al crear una matriz de argumentos de tipo y llamar al método <xref:System.Type.MakeGenericType%2A>. El programa compara el objeto <xref:System.Type> construido mediante <xref:System.Type.MakeGenericType%2A> con un objeto <xref:System.Type> obtenido mediante `typeof` (`GetType` en Visual Basic) y muestra que son iguales. Del mismo modo, el programa usa el método <xref:System.Type.GetGenericTypeDefinition%2A> para obtener la definición de tipo genérico del tipo construido y lo compara con el objeto <xref:System.Type> que representa a la clase <xref:System.Collections.Generic.Dictionary%602>.  
  
 [!code-cpp[HowToGeneric#1](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#1)]
 [!code-csharp[HowToGeneric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#1)]
 [!code-vb[HowToGeneric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#1)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Type>
- <xref:System.Reflection.MethodInfo>
- [Reflexión y tipos genéricos](reflection-and-generic-types.md)
- [Ver información tipos](viewing-type-information.md)
- [Genéricos](../../standard/generics/index.md)
