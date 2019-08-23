---
title: -codePage (Visual Basic)
ms.date: 03/09/2018
helpviewer_keywords:
- -codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
ms.openlocfilehash: 3a5974a910303f847679f18c23e00cfaa00caa2c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962609"
---
# <a name="-codepage-visual-basic"></a>-codePage (Visual Basic)
Especifica la página de códigos que se va a utilizar para todos los archivos de código fuente en la compilación.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-codepage:id  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`id`|Necesario. El compilador usa la página de `id` códigos especificada por para interpretar la codificación de los archivos de código fuente.|  
  
## <a name="remarks"></a>Comentarios  
 Para compilar el código fuente guardado con una codificación específica, puede `-codepage` usar para especificar qué página de códigos debe usarse. La `-codepage` opción se aplica a todos los archivos de código fuente de la compilación. Para obtener más información, vea [codificación de caracteres en el .NET Framework](../../../standard/base-types/character-encoding.md).  
  
 La `-codepage` opción no es necesaria si los archivos de código fuente se guardaron mediante la página de códigos ANSI actual, Unicode o UTF-8 con una firma. De forma predeterminada, Visual Studio guarda todos los archivos de código fuente con la página de códigos ANSI actual, a menos que el usuario especifique otra codificación en el cuadro de diálogo **codificación** . Visual Studio usa el cuadro de diálogo **codificación** para abrir los archivos de código fuente guardados con una página de códigos diferente.  
  
> [!NOTE]
> La `-codepage` opción no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible al compilar desde la línea de comandos.  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
