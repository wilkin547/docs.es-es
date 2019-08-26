---
title: 'Procedimiento Definir propiedades abstractas: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], abstract
- abstract properties [C#]
ms.assetid: 672a90eb-47b9-4ae0-9914-af53852fddcb
ms.openlocfilehash: fae526f5dcd452fbc381ee86c892b72e61956f0b
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69596867"
---
# <a name="how-to-define-abstract-properties-c-programming-guide"></a>Procedimiento Definir propiedades abstractas (Guía de programación de C#)
En el ejemplo siguiente se muestra cómo definir las propiedades [abstract](../../language-reference/keywords/abstract.md). Una declaración de propiedad abstracta no proporciona una implementación de los descriptores de acceso de propiedad, declara que la clase admite propiedades, pero deja la implementación del descriptor de acceso a las clases derivadas. En el ejemplo siguiente se muestra cómo implementar las propiedades abstractas heredadas de una clase base.  
  
 Este ejemplo consta de tres archivos, cada uno de los cuales se compila individualmente y se hace referencia a su ensamblado resultante mediante la siguiente compilación:  
  
- abstractshape.cs: la clase `Shape` que contiene una propiedad `Area` abstracta.  
  
- shapes.cs: las subclases de la clase `Shape`.  
  
- shapetest.cs: un programa de prueba para mostrar las áreas de algunos objetos derivados de `Shape`.  
  
 Para compilar el ejemplo, use el siguiente comando:  
  
 `csc abstractshape.cs shapes.cs shapetest.cs`  
  
 Esto creará el archivo ejecutable shapetest.exe.  
  
## <a name="example"></a>Ejemplo  
 Este archivo declara la clase `Shape` que contiene la propiedad `Area` del tipo `double`.  
  
 [!code-csharp[csProgGuideInheritance#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#1)]  
  
- Los modificadores de la propiedad se colocan en la propia declaración de propiedad. Por ejemplo:  
  
    ```csharp  
    public abstract double Area  
    ```  
  
- Al declarar una propiedad abstracta (como `Area` en este ejemplo), simplemente indica qué descriptores de acceso de propiedad están disponibles, pero no los implementa. En este ejemplo, solo está disponible un descriptor de acceso [get](../../language-reference/keywords/get.md), por lo que la propiedad es de solo lectura.  
  
## <a name="example"></a>Ejemplo  
 En el siguiente código se muestran tres subclases de `Shape` y cómo invalidan la propiedad `Area` para proporcionar su propia implementación.  
  
 [!code-csharp[csProgGuideInheritance#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#2)]  
  
## <a name="example"></a>Ejemplo  
 En el siguiente código se muestra un programa de prueba que crea un número de objetos derivados de `Shape` e imprime sus áreas.  
  
 [!code-csharp[csProgGuideInheritance#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#3)]  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Clases y structs](./index.md)
- [Clases y miembros de clase abstractos y sellados](./abstract-and-sealed-classes-and-class-members.md)
- [Propiedades](./properties.md)
- [Cómo: Crear y utilizar ensamblados mediante la línea de comandos](../concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md).
