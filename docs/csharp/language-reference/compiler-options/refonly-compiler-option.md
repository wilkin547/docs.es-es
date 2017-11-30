---
title: -refonly (Opciones del compilador de C#)
ms.date: 07/08/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /refonly
helpviewer_keywords:
- /refonly compiler option [C#]
- -refonly compiler option [C#]
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c4c745416bda56f5f1b1b4ab8267274d972a990d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="refonly-c-compiler-options"></a>/refonly (Opciones del compilador de C#)

El **/refonly** opción indica que un ensamblado de referencia deben mostrarse en lugar de un ensamblado de implementación, como el resultado principal. El parámetro `/refonly` deshabilita de forma automática la generación de archivos PDB, ya que los ensamblados de referencia no pueden ejecutarse.

## <a name="syntax"></a>Sintaxis

```console
/refonly
```

## <a name="remarks"></a>Comentarios

Los ensamblados de solo metadatos tienen sus cuerpos de métodos reemplazados por un cuerpo `throw null` único, pero incluyen todos los miembros excepto los tipos anónimos. El motivo de usar cuerpos `throw null` (en lugar de no usar ningún cuerpo) es que PEVerify pueda ejecutar y pasar (por lo tanto, validar la integridad de los metadatos).

Los ensamblados de referencia incluyen un atributo `ReferenceAssembly` de nivel de ensamblado. Este atributo puede especificarse en el origen (por lo tanto, el compilador no necesitará sintetizarlo). Debido a este atributo, los tiempos de ejecución rechazarán cargar ensamblados de referencia para su ejecución (pero todavía pueden cargarse en modo de solo reflexión). Las herramientas que se reflejan en ensamblados necesitan asegurarse de que cargan ensamblados de referencia en el modo de solo reflexión, de otro modo, recibirán un error typeload del runtime.

Los ensamblados de referencia también quitan los metadatos (miembros privados) de los ensamblados de solo metadatos:

- Un ensamblado de referencia solo tiene referencias para lo que necesita en la superficie de la API. El ensamblado real puede tener referencias adicionales relacionadas con las implementaciones específicas. Por ejemplo, el ensamblado de referencia de `class C { private void M() { dynamic d = 1; ... } }` no hace referencia a ningún tipo necesario para `dynamic`.
- Los miembros de función privados (métodos, propiedades y eventos) se quitan en los casos donde su retirada no afecta a la compilación de manera visible. Si no hay ningún atributo `InternalsVisibleTo`, haga lo mismo para los miembros de función internos.
- Pero todos los tipos (incluidos los tipos anidados o privados) se conservan en los ensamblados de referencia. Se conservan todos los atributos (incluso los internos).
- Se conservan todos los métodos virtuales. Se mantienen las implementaciones explícitas de interfaces. Se conservan los eventos y propiedades que se han implementado explícitamente, ya que sus descriptores de acceso son virtuales (y por lo tanto se conservan).
- Se conservan todos los campos de un struct. (Es un candidato para el refinamiento posterior de C#-7.1)

Las opciones `/refonly` y [`/refout`](refout-compiler-option.md) son mutuamente excluyentes.

## <a name="see-also"></a>Vea también
 [Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md)  
 [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)
