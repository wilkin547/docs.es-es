---
title: Procedimiento para saber las diferencias entre pasar a un método un struct y una referencia a clase - Guía de programación de C#
description: El proceso de pasar un struct a un método es diferente de pasar una instancia de clase a un método en C#. En este ejemplo se muestra la instancia de struct y de clase pasada por valor.
ms.date: 07/20/2015
helpviewer_keywords:
- structs [C#], passing as method parameter
- passing parameters [C#], structs vs. classes
- methods [C#], passing classes vs. structs
ms.topic: how-to
ms.custom: contperf-fy21q2
ms.assetid: 9c1313a6-32a8-4ea7-a59f-450f66af628b
ms.openlocfilehash: a4d969617b450fcd788764e97afe3aa1ff19a48c
ms.sourcegitcommit: 8299abfbd5c49b596d61f1e4d09bc6b8ba055b36
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2021
ms.locfileid: "98898806"
---
# <a name="how-to-know-the-difference-between-passing-a-struct-and-passing-a-class-reference-to-a-method-c-programming-guide"></a>Procedimiento para saber las diferencias entre pasar a un método un struct y una referencia a clase (Guía de programación de C#)

En el ejemplo siguiente se muestra cómo pasar un [struct](../../language-reference/builtin-types/struct.md) a un método es diferente de pasar una instancia de [clase](../../language-reference/keywords/class.md) a un método. En el ejemplo, los dos argumentos (struct e instancia de clase) se pasan mediante valor, y ambos métodos cambian el valor de un campo del argumento. En cambio, los resultados de los dos métodos no son los mismos porque lo que se pasa cuando pasa un struct difiere de lo que se pasa cuando pasa una instancia de una clase.  
  
 Como un struct es un [tipo de valor](../../language-reference/builtin-types/value-types.md), cuando [pasa un struct mediante valor](./passing-value-type-parameters.md) a un método, el método recibe y funciona en una copia del argumento struct. El método no tiene acceso al struct original en el método de llamada y, por lo tanto, no puede cambiarlo de ninguna manera. El método solo puede cambiar la copia.  
  
 Una instancia de clase es un [tipo de referencia](../../language-reference/keywords/reference-types.md), no un tipo de valor. Cuando [un tipo de referencia se pasa mediante valor](./passing-reference-type-parameters.md) a un método, el método recibe una copia de la referencia a la instancia de clase. Es decir, el método al que se llama recibe una copia de la dirección de la instancia y el método de llamada conserva la dirección original de la instancia. La instancia de clase en el método de llamada tiene una dirección, el parámetro en el método que se ha llamado tiene una copia de la dirección, y ambas direcciones hacen referencia al mismo objeto. Como el parámetro solo contiene una copia de la dirección, el método al que se ha llamado no puede cambiar la dirección de la instancia de clase en el método de llamada. En cambio, el método al que se ha llamado puede usar la copia de la dirección para acceder a los miembros de clase a los que hacen referencia la dirección original y la copia de la dirección. Si el método al que se ha llamado cambia un miembro de clase, la instancia de clase original en el método de llamada también cambia.  
  
 En el resultado del ejemplo siguiente se ilustra la diferencia. El valor del campo `willIChange` de la instancia de clase se cambia mediante la llamada al método `ClassTaker` porque el método usa la dirección en el parámetro para buscar el campo especificado de la instancia de clase. El campo `willIChange` del struct en el método de llamada no se cambia mediante la llamada al método `StructTaker` porque el valor del argumento es una copia del propio struct, no una copia de su dirección. `StructTaker` cambia la copia, y la copia se pierde cuando se completa la llamada a `StructTaker`.  
  
## <a name="example"></a>Ejemplo  

 [!code-csharp[PassingStructVsClass](snippets/how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method/Program.cs)]  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Clases](./classes.md)
- [Tipos de estructura](../../language-reference/builtin-types/struct.md)
- [Pasar parámetros](./passing-parameters.md)
