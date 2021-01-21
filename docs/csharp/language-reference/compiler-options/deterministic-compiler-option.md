---
description: -deterministic (opciones del compilador de C#)
title: -deterministic (opciones del compilador de C#)
ms.date: 04/12/2018
f1_keywords:
- /deterministic
helpviewer_keywords:
- -deterministic compiler option [C#]
- deterministic compiler option [C#]
- /deterministic compiler option [C#]
ms.openlocfilehash: d64f4d4b0d4e9b5ed2cc1ee40662dc669fc6660d
ms.sourcegitcommit: 4f5f1855849cb02c3b610c7006ac21d7429f3348
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "98235331"
---
# <a name="-deterministic"></a>-deterministic

Hace que el compilador genere un ensamblado cuya salida byte a byte es idéntica en todas las compilaciones para las entradas idénticas.

## <a name="syntax"></a>Sintaxis

```console
-deterministic
```

## <a name="remarks"></a>Comentarios

De forma predeterminada, la salida del compilador de un conjunto determinado de entradas es única, ya que el compilador agrega una marca de tiempo y un MVID que se genera a partir de números aleatorios. Use la opción `-deterministic` para generar un *ensamblado determinista*, cuyo contenido binario es idéntico en todas las compilaciones, siempre y cuando la entrada siga siendo la misma. En este tipo de compilación, los campos timestamp y MVID se reemplazarán por los valores derivados de un hash de todas las entradas de la compilación.

El compilador tiene en cuenta las entradas siguientes con el fin de garantizar el determinismo:

- La secuencia de parámetros de la línea de comandos.
- El contenido del archivo de respuesta .rsp del compilador.
- La versión exacta del compilador que se usa y los ensamblados a los que se hace referencia.
- La ruta de acceso del directorio actual.
- El contenido binario de todos los archivos pasados explícitamente al compilador, ya sea de manera directa o indirecta, incluidos los siguientes:
  - Archivos de código fuente
  - Ensamblados a los que se hace referencia
  - Módulos a los que se hace referencia
  - Recursos
  - Archivo de clave de nombre seguro
  - Archivos de respuesta @
  - Analizadores
  - Conjuntos de reglas
  - Archivos adicionales que podrían usar los analizadores
- La referencia cultural actual (para el idioma en el que se producen los diagnósticos y los mensajes de excepción).
- La codificación predeterminada (o página de códigos actual) si no se especifica la codificación.
- La existencia (o la inexistencia) de archivos y su contenido en las rutas de búsqueda del compilador (especificada, por ejemplo, mediante `-lib` o `-recurse`).
- La plataforma CLR en la que se ejecuta el compilador.
- El valor de `%LIBPATH%`, que pueden afectar a la carga de dependencias del analizador.

Cuando los orígenes están disponibles públicamente, se puede usar la compilación determinista para establecer si un archivo binario se compila a partir de una fuente de confianza. También puede ser útil en un sistema de compilación continua para determinar si es necesario ejecutar pasos de compilación que dependen de los cambios realizados en un archivo binario.

## <a name="see-also"></a>Vea también

- [Opciones del compilador de C#](./index.md)
- [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)
