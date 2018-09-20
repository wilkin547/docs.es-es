---
title: -codepage (Visual Basic)
ms.date: 03/09/2018
helpviewer_keywords:
- -codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
ms.openlocfilehash: fda75383435fdff718d1d50bc8583afc9858e7e2
ms.sourcegitcommit: f513a91160b3fec289dd06646d0d6f81f8fcf910
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46320944"
---
# <a name="-codepage-visual-basic"></a>-codepage (Visual Basic)
Especifica la página de códigos que se va a utilizar para todos los archivos de código fuente en la compilación.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-codepage:id  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`id`|Requerido. El compilador usa la página de códigos especificada por `id` para interpretar la codificación de los archivos de origen.|  
  
## <a name="remarks"></a>Comentarios  
 Para compilar código fuente guardado con una codificación específica, puede usar `-codepage` para especificar qué página de códigos debe usarse. El `-codepage` opción se aplica a todos los archivos de código fuente de la compilación. Para obtener más información, consulte [codificación de caracteres en .NET Framework](../../../standard/base-types/character-encoding.md).  
  
 El `-codepage` opción no es necesario si se guardaron los archivos de código fuente utilizando la página de códigos ANSI actual, Unicode o UTF-8 con una firma. Visual Studio guarda todos los archivos de código fuente con la página de códigos ANSI actual de forma predeterminada, a menos que el usuario especifique otra codificación en el **Encoding** cuadro de diálogo. Visual Studio usa el **Encoding** cuadro de diálogo para abrir archivos de código fuente que se guardan con una página de códigos diferentes.  
  
> [!NOTE]
>  El `-codepage` opción no está disponible en el entorno de desarrollo de Visual Studio; está disponible solo cuando se compila desde la línea de comandos.  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
