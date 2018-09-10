---
title: -refout (Opciones del compilador de C#)
ms.date: 08/08/2017
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [C#]
- /refout compiler option [C#]
- -refout compiler option [C#]
ms.openlocfilehash: e204a053f6f68a4b848d22c95c98f04edff58716
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43506630"
---
# <a name="-refout-c-compiler-options"></a>-refout (Opciones del compilador de C#)

La opción **-refout** especifica una ruta de archivo donde el ensamblado de referencia debe mostrarse. Esto se traduce en `metadataPeStream` en la API de emisión.

## <a name="syntax"></a>Sintaxis

```console
-refout:filepath
```

## <a name="arguments"></a>Argumentos

 `filepath` La ruta de archivo del ensamblado de referencia. Generalmente debe coincidir con el ensamblado principal. La convención recomendada (que se usa por MSBuild) es colocar el ensamblado de referencia en una subcarpeta "ref/" con relación al ensamblado principal.

## <a name="remarks"></a>Comentarios

Los ensamblados de solo metadatos tienen sus cuerpos de métodos reemplazados por un cuerpo `throw null` único, pero incluyen todos los miembros excepto los tipos anónimos. El motivo de usar cuerpos `throw null` (en lugar de no usar ningún cuerpo) es que PEVerify pueda ejecutar y pasar (por lo tanto, validar la integridad de los metadatos).

Los ensamblados de referencia incluyen un atributo `ReferenceAssembly` de nivel de ensamblado. Este atributo puede especificarse en el origen (por lo tanto, el compilador no necesitará sintetizarlo). Debido a este atributo, los tiempos de ejecución rechazarán cargar ensamblados de referencia para su ejecución (pero todavía pueden cargarse en modo de solo reflexión). Las herramientas que se reflejan en ensamblados necesitan asegurarse de que cargan ensamblados de referencia en el modo de solo reflexión, de otro modo, recibirán un error typeload del runtime.

Los ensamblados de referencia también quitan los metadatos (miembros privados) de los ensamblados de solo metadatos:

- Un ensamblado de referencia solo tiene referencias para lo que necesita en la superficie de la API. El ensamblado real puede tener referencias adicionales relacionadas con las implementaciones específicas. Por ejemplo, el ensamblado de referencia de `class C { private void M() { dynamic d = 1; ... } }` no hace referencia a ningún tipo necesario para `dynamic`.
- Los miembros de función privados (métodos, propiedades y eventos) se quitan en los casos donde su retirada no afecta a la compilación de manera visible. Si no hay ningún atributo `InternalsVisibleTo`, haga lo mismo para los miembros de función internos.
- Pero todos los tipos (incluidos los tipos anidados o privados) se conservan en los ensamblados de referencia. Se conservan todos los atributos (incluso los internos).
- Se conservan todos los métodos virtuales. Se mantienen las implementaciones explícitas de interfaces. Se conservan los eventos y propiedades que se han implementado explícitamente, ya que sus descriptores de acceso son virtuales (y por lo tanto se conservan).
- Se conservan todos los campos de un struct. (Es un candidato para el refinamiento posterior de C#-7.1)

Las opciones `-refout` y [`-refonly`](refonly-compiler-option.md) son mutuamente excluyentes.

## <a name="see-also"></a>Vea también

- [Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md)  
- [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)
