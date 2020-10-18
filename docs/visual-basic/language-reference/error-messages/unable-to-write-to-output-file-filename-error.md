---
title: "No se puede escribir en el archivo de resultados '<filename>': <error>"
ms.date: 07/20/2015
f1_keywords:
- vbc31019
- bc31019
helpviewer_keywords:
- BC31019
ms.assetid: 0845b245-11bb-46fd-95ca-f6cef3c318ef
ms.openlocfilehash: 5f4add95da7c996513ffb291a7794ea0e345ac94
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161548"
---
# <a name="bc31019-unable-to-write-to-output-file-filename-error"></a>BC31019: no se puede escribir en el archivo de salida ' \<filename> ': \<error>

Se ha producido un problema al crear el archivo.

 No se puede abrir un archivo de salida para escritura. Puede que otro proceso haya abierto el archivo (o la carpeta que lo contiene) o puede que este tenga establecido el atributo de solo lectura.

 A continuación indicamos las situaciones más habituales en la que un archivo se abre de forma exclusiva:

- La aplicación ya se está ejecutando y usando sus archivos. Para solucionar este problema, asegúrese de que la aplicación no se está ejecutando.

- Otra aplicación ha abierto el archivo. Para solucionar este problema, asegúrese de que ninguna otra aplicación está accediendo a los archivos. No siempre queda del todo claro qué aplicación está accediendo a los archivos; en tal caso, reiniciar el equipo constituye la forma más sencilla de finalizar la aplicación.

 Esta excepción se generará aun cuando solo haya un archivo de salida del proyecto marcado como de solo lectura.

 **Identificador de error:** BC31019

## <a name="to-correct-this-error"></a>Para corregir este error

1. Vuelva a compilar el programa para ver si el error se repite.

2. Si el error continúa, guarde el trabajo y reinicie Visual Studio.

3. Si el error continúa, reinicie el equipo.

4. Si el error se repite, reinstale Visual Basic.

5. Si el error persiste después de la reinstalación, informe al respecto a los Servicios de soporte técnico de Microsoft.

### <a name="to-check-file-attributes-in-file-explorer"></a>Para consultar los atributos de archivo en el Explorador de archivos

1. Abra la carpeta que le interese.

2. Haga clic en el icono **vistas** y elija **detalles**.

3. Haga clic con el botón secundario en el encabezado de columna y elija **atributos** en la lista desplegable.

### <a name="to-change-the-attributes-of-a-file-or-folder"></a>Para cambiar los atributos de un archivo o carpeta

1. En el **Explorador de archivos**, haga clic con el botón derecho en el archivo o la carpeta y elija **propiedades**.

2. En la sección **atributos** de la ficha **General** , desactive la casilla **solo lectura** .

3. Haga clic en **Aceptar**.

## <a name="see-also"></a>Vea también

- [Hable con nosotros](/visualstudio/ide/feedback-options)
