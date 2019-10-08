---
title: -codePage (Visual Basic)
ms.date: 03/09/2018
helpviewer_keywords:
- -codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
ms.openlocfilehash: e4cdc27ab021fe055f157b78946538f2b76870e1
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002363"
---
# <a name="-codepage-visual-basic"></a>-codePage (Visual Basic)
Especifica la página de códigos que se va a utilizar para todos los archivos de código fuente en la compilación.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-codepage:id  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`id`|Obligatorio. El compilador usa la página de códigos especificada por `id` para interpretar la codificación de los archivos de código fuente.|  
  
## <a name="remarks"></a>Comentarios  
 Para compilar el código fuente guardado con una codificación específica, puede usar `-codepage` para especificar la página de códigos que se debe usar. La opción `-codepage` se aplica a todos los archivos de código fuente de la compilación. Para obtener más información, vea [codificación de caracteres en el .NET Framework](../../../standard/base-types/character-encoding.md).  
  
 La opción `-codepage` no es necesaria si los archivos de código fuente se guardaron mediante la página de códigos ANSI actual, Unicode o UTF-8 con una firma. De forma predeterminada, Visual Studio guarda todos los archivos de código fuente con la página de códigos ANSI actual, a menos que el usuario especifique otra codificación en el cuadro de diálogo **codificación** . Visual Studio usa el cuadro de diálogo **codificación** para abrir los archivos de código fuente guardados con una página de códigos diferente.  
  
> [!NOTE]
> La opción `-codepage` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible al compilar desde la línea de comandos.  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
