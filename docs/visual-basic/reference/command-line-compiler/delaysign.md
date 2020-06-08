---
title: -delaysign
ms.date: 03/10/2018
helpviewer_keywords:
- delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
ms.openlocfilehash: c9bb302e2b34ebe1f51cf39bb3db1094d420d7f4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408704"
---
# <a name="-delaysign"></a>-delaysign

Especifica si el ensamblado estará firmado total o parcialmente.

## <a name="syntax"></a>Sintaxis

```console
-delaysign[+ | -]
```

## <a name="arguments"></a>Argumentos

`+` &#124; `-`  
Opcional. Use `-delaysign-` para firmar completamente un ensamblado. Use `-delaysign+` si quiere colocar la clave pública en el ensamblado y reservar espacio para el hash firmado. De manera predeterminada, es `-delaysign-`.

## <a name="remarks"></a>Comentarios

La opción `-delaysign` no tiene ningún efecto a menos que se use con [-keyfile](keyfile.md) o [-keycontainer](keycontainer.md).

Cuando se solicita un ensamblado totalmente firmado, el compilador genera un valor hash para el archivo que contiene el manifiesto (metadatos del ensamblado) y firma dicho valor mediante la clave privada. La firma digital resultante se almacena en el archivo que contiene el manifiesto. Si se retrasa la firma de un ensamblado, el compilador no calcula ni almacena la firma, sino que reserva espacio en el archivo para que la firma se pueda agregar más tarde.

Por ejemplo, mediante el uso de `-delaysign+`, un desarrollador de una organización puede distribuir versiones de prueba sin firmar de un ensamblado que los evaluadores pueden registrar con la caché global de ensamblados y usar. Cuando se completa el trabajo en el ensamblado, la persona responsable de la clave privada de la organización puede firmar completamente el ensamblado. Esta compartimentación protege la clave privada de la organización contra la divulgación, a la vez que permite que todos los desarrolladores trabajen en los ensamblados.

Para obtener más información sobre cómo firmar un ensamblado, vea [Crear y utilizar ensamblados con nombre seguro](../../../standard/assembly/create-use-strong-named.md).

### <a name="to-set--delaysign-in-the-visual-studio-integrated-development-environment"></a>Para establecer -delaysign en el entorno de desarrollo integrado de Visual Studio

1. Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**.

2. Haga clic en la pestaña **Firma**.

3. Establezca el valor en el cuadro **Solo retrasar firma**.

## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](index.md)
- [-keyfile](keyfile.md)
- [-keycontainer](keycontainer.md)
- [Líneas de comandos de compilación de ejemplo](sample-compilation-command-lines.md)
