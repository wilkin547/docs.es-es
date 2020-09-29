---
title: -codepage
ms.date: 03/09/2018
helpviewer_keywords:
- -codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
ms.openlocfilehash: 769f3586ddef7f430fa96d6101b250a5bbc4e26c
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91065741"
---
# <a name="-codepage-visual-basic"></a>-codepage (Visual Basic)

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

 Para compilar el código fuente guardado con una codificación específica, puede usar `-codepage` para especificar qué página de códigos debe usarse. La opción `-codepage` se aplica a todos los archivos de código fuente de la compilación. Para más información, consulte [Codificación de caracteres en .NET Framework](../../../standard/base-types/character-encoding.md).  
  
 La opción `-codepage` no es necesaria si los archivos de código fuente se han guardado mediante la página actual de códigos ANSI, Unicode o UTF-8 con una firma. De forma predeterminada, Visual Studio guarda todos los archivos de código fuente con la página de códigos ANSI actual, a menos que el usuario especifique otra codificación en el cuadro de diálogo **Codificación**. Visual Studio usa el cuadro de diálogo **Codificación** para abrir los archivos de código fuente guardados con una página de códigos diferente.  
  
> [!NOTE]
> La opción `-codepage` no está disponible en el entorno de desarrollo de Visual Studio; solo lo está cuando se compila desde la línea de comandos.  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](index.md)
