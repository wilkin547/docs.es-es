---
title: Reglas de uso (análisis de código)
description: Más información sobre las reglas de uso de análisis de código.
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.codeanalysis.usagerules
helpviewer_keywords:
- rules, usage
- managed code analysis rules, usage rules
- usage rules
author: gewarren
ms.author: gewarren
ms.openlocfilehash: c8b14d2f92502d5a82e41a322e599745bdcf8b85
ms.sourcegitcommit: a6bd4cad438fe479cbd112eae10f2cd449f06e40
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2020
ms.locfileid: "96594531"
---
# <a name="usage-rules"></a>Reglas de uso

Las reglas de uso admiten el uso adecuado de .NET.

## <a name="in-this-section"></a>En esta sección

|Regla|Descripción|
|----------|-----------------|
|[CA1801: Revisar parámetros sin utilizar](ca1801.md)|Una firma de método incluye un parámetro que no se utiliza en el cuerpo del método.|
|[CA1816: Llamar a GC.SuppressFinalize correctamente](ca1816.md)|Un método que es una implementación de Dispose no llama a `GC.SuppressFinalize` ; o a un método que no es una implementación de `Dispose` llamadas `GC.SuppressFinalize` ; o a un método llama a `GC.SuppressFinalize` y pasa un valor distinto de `this` ( `Me` en Visual Basic).|
|[CA2200: Reiniciar para mantener los detalles de la pila](ca2200.md)|Se vuelve a producir una excepción y se especifica explícitamente en la instrucción throw. Si se vuelve a producir una excepción especificándola en la instrucción throw, se pierde la lista de llamadas al método entre el método original que produjo la excepción y el método actual.|
|[CA2201: No provocar tipos de excepción reservados](ca2201.md)|Esto hace que el error original sea difícil de detectar y depurar.|
|[CA2207: Inicializar campos estáticos de tipo de valor insertados](ca2207.md)|Un tipo de valor declara un constructor estático explícito. Para corregir una infracción de esta regla, inicialice todos los datos estáticos cuando se declara y quite el constructor estático.|
|[CA2208: Crear instancias de las excepciones del argumento correctamente](ca2208.md)|Se realiza una llamada al constructor predeterminado (sin parámetros) de un tipo de excepción que es o deriva de ArgumentException, o se pasa un argumento de cadena incorrecto a un constructor con parámetros de un tipo de excepción que es o deriva de ArgumentException.|
|[CA2211: Los campos no constantes no deben ser visibles](ca2211.md)|Los campos estáticos que no son constantes o de solo lectura no son seguros para subprocesos. El acceso a este tipo de campo debe controlarse cuidadosamente y requiere técnicas de programación avanzada para sincronizar el acceso al objeto de clase.|
|[CA2213: Los campos descartables deben ser descartables](ca2213.md)|Un tipo que implementa <xref:System.IDisposable?displayProperty=fullName> declara campos que son de tipos que también implementan `IDisposable` . El método del `Dispose` tipo declarativo no llama al método del campo `Dispose` .|
|[CA2214: No llamar a métodos reemplazables en constructores](ca2214.md)|Cuando un constructor llama a un método virtual, es posible que no se haya ejecutado el constructor de la instancia que invoca el método.|
|[CA2215: Los métodos Dispose deben llamar al método Dispose de la clase base](ca2215.md)|Si un tipo hereda de un tipo descartable, debe llamar al `Dispose` método del tipo base desde su propio `Dispose` método.|
|[CA2216: Los tipos descartables deben declarar el finalizador](ca2216.md)|Un tipo que implementa <xref:System.IDisposable?displayProperty=fullName> , y tiene campos que sugieren el uso de recursos no administrados, no implementa un finalizador tal como se describe en `Object.Finalize` .|
|[CA2217: No marcar enumeraciones con FlagsAttribute](ca2217.md)|Una enumeración visible externamente está marcada con `FlagsAttribute` y tiene uno o más valores que no son potencias de dos o una combinación de los demás valores definidos en la enumeración.|
|[CA2218: Invalidar el método GetHashCode al invalidar el método Equals](ca2218.md)|Un tipo público invalida pero no <xref:System.Object.Equals%2A?displayProperty=fullName> invalida <xref:System.Object.GetHashCode%2A?displayProperty=fullName> .|
|[CA2219: No producir excepciones en cláusulas de excepción](ca2219.md)|Cuando se genera una excepción en una cláusula finally o fault, la nueva excepción oculta la excepción activa. Cuando se genera una excepción en una cláusula filter, el runtime la detecta automáticamente. Esto hace que el error original sea difícil de detectar y depurar.|
|[CA2224: Invalidar Equals al sobrecargar operadores de igualdad](ca2224.md)|Un tipo público implementa el operador de igualdad pero no invalida <xref:System.Object.Equals%2A?displayProperty=fullName> .|
|[CA2225: Las sobrecargas del operador tienen alternativas con nombre](ca2225.md)|Se detectó una sobrecarga del operador y no se encontró el método alternativo con el nombre esperado. El miembro alternativo con nombre proporciona acceso a la misma funcionalidad que el operador y se proporciona a los desarrolladores que programan en lenguajes que no admiten operadores sobrecargados.|
|[CA2226: Los operadores deben tener sobrecargas simétricas](ca2226.md)|Un tipo implementa el operador de igualdad o desigualdad y no implementa el operador opuesto.|
|[CA2227: Las propiedades de la colección deben ser de solo lectura](ca2227.md)|Una propiedad de colección grabable permite al usuario reemplazar la colección por otra diferente. Una propiedad de sólo lectura impide que la colección se reemplace, pero sí permite establecer miembros individuales.|
|[CA2229: Implementar constructores de serialización](ca2229.md)|Para corregir una infracción de esta regla, implemente el constructor de serialización. Para una clase sellada, marque el constructor como privado; de lo contrario, márquelo como protegido.|
|[CA2231: Sobrecargar el operador equals al invalidar ValueType.Equals](ca2231.md)|Un tipo de valor invalida `Object.Equals` pero no implementa el operador de igualdad.|
|[CA2234: Pasar objetos System.Uri en lugar de cadenas](ca2234.md)|Se realiza una llamada a un método que tiene un parámetro de cadena cuyo nombre contiene "uri", "URI", "urn", "URN", "url" o "URL".  El tipo declarativo del método contiene una sobrecarga de método correspondiente que tiene un <xref:System.Uri?displayProperty=fullName> parámetro.|
|[CA2235: Marcar todos los campos no serializables](ca2235.md)|Un campo de instancia de un tipo que no es serializable se declara en un tipo que es serializable.|
|[CA2237: Marcar los tipos ISerializable con SerializableAttribute](ca2237.md)|Para ser reconocibles por el Common Language Runtime como serializable, los tipos se deben marcar con el atributo SerializableAttribute incluso si el tipo utiliza una rutina de serialización personalizada a través de la implementación de la `ISerializable` interfaz.|
|[CA2241: Proporcionar argumentos correctos a los métodos de formato](ca2241.md)|El argumento de formato pasado a no <xref:System.String.Format%2A?displayProperty=nameWithType> contiene un elemento de formato que corresponda a cada argumento de objeto, o viceversa.|
|[CA2242: Comprobar NaN correctamente](ca2242.md)|Esta expresión prueba un valor con `Single.Nan` o `Double.Nan` . Use `Single.IsNan(Single)` o `Double.IsNan(Double)` para probar el valor.|
|[CA2243: Los literales de cadena de atributo se deben analizar correctamente](ca2243.md)|El parámetro de literal de cadena de un atributo no se analiza correctamente para una dirección URL, un GUID o una versión.|
|[CA2244: No duplicar inicializaciones de elementos indexados](ca2244.md)|Un inicializador de objeto tiene más de un inicializador de elemento indizado con el mismo índice de constante. Todo menos el último inicializador son redundantes.|
|[CA2245: No asignar una propiedad a sí misma](ca2245.md)|Una propiedad se asignó accidentalmente a sí misma.|
|[CA2246: No asignar un símbolo y su miembro en la misma instrucción](ca2246.md)|No se recomienda asignar un símbolo y su miembro, es decir, un campo o una propiedad, en la misma instrucción. No está claro si el acceso a miembros debía usar el valor anterior del símbolo antes de la asignación o el nuevo valor de la asignación en esta instrucción.|
|[CA2247: El argumento pasado al constructor TaskCompletionSource debe ser una enumeración TaskCreationOptions en lugar de TaskContinuationOptions](ca2246.md)|TaskCompletionSource tiene constructores que toman un TaskCreationOptions que controla la tarea subyacente y constructores que toman el estado del objeto almacenado en la tarea.  Pasar accidentalmente un TaskContinuationOptions en lugar de un TaskCreationOptions dará lugar a que la llamada trate las opciones como estado.|
|[CA2248: proporcione el argumento ' ENUM ' correcto a ' enum. HasFlag '](ca2248.md)|El tipo de enumeración que se pasa como argumento a la `HasFlag` llamada al método es diferente del tipo de enumeración que realiza la llamada.|
|[CA2249: Valorar la posibilidad de usar String.Contains en lugar de String.IndexOf](ca2249.md)|Las llamadas a `string.IndexOf` donde se utiliza el resultado para comprobar la presencia o la ausencia de una subcadena se pueden reemplazar por `string.Contains` .|
