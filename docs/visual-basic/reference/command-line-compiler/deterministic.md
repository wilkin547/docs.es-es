---
title: -determinista
ms.date: 04/11/2018
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- deterministic compiler option [Visual Basic]
- -deterministic compiler option [Visual Basic]
- -deterministic compiler option [Visual Basic]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 273abf8811f04cd7f58599ce3421ca1f17c740d9
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2018
---
# <a name="-deterministic"></a>-determinista

Hace que el compilador generar un ensamblado cuyo resultado byte a byte es idéntica en compilaciones para las mismas entradas. 

## <a name="syntax"></a>Sintaxis

```
-deterministic
```

## <a name="remarks"></a>Comentarios

De forma predeterminada, resultados del compilador de un conjunto determinado de entradas es único, ya que el compilador agrega una marca de tiempo y un GUID que se genera a partir de números aleatorios. Usa el `-deterministic` opción para generar un *ensamblado determinista*, uno cuyo contenido binario es idéntico a través de las compilaciones, siempre y cuando la entrada sigue siendo el mismo.

El compilador considera que las entradas siguientes con el fin de determinismo:

- La secuencia de parámetros de línea de comandos.
- El contenido del archivo de respuesta del compilador rsp.
- La versión exacta del compilador utilizada y sus ensamblados que se hace referencia.
- La ruta del directorio actual.
- El contenido binario de todos los archivos explícitamente pasó al compilador directa o indirectamente, incluidos: 
    - Archivos de código fuente
    - ensamblados de referencia
    - Módulos que se hace referencia
    - Recursos
    - El archivo de clave de nombre seguro
    - @ archivos de respuesta
    - Analizadores
    - Conjuntos de reglas
    - Archivos adicionales que pueden utilizarse analizadores
- La referencia cultural actual (para el idioma en qué diagnósticos y las excepciones se producen mensajes).
- La codificación predeterminada (o la página de códigos actual) si no se especifica la codificación.
- La existencia, la existencia no y el contenido de los archivos en las rutas de búsqueda del compilador (especificado, por ejemplo, `/lib` o `/recurse`).
- La plataforma CLR en el que se ejecuta el compilador.
- El valor de `%LIBPATH%`, que pueden afectar a la carga de la dependencia de analizador.

Cuando los orígenes disponibles públicamente, compilación determinista puede usarse para establecer si se compila un archivo binario de una fuente confiable. También puede ser útil en un sistema de compilación continua para determinar si deben ejecutar pasos de compilación que dependen de los cambios en un archivo binario. 

## <a name="see-also"></a>Vea también
[Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
[Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
