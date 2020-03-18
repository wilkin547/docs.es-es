---
title: CorFlags.exe (Herramienta de conversión de CorFlags)
ms.date: 03/30/2017
helpviewer_keywords:
- CorFlags conversion tool
- CorFlags.exe
- portable executable files, CorFlags section
ms.assetid: ef900f8f-71ca-4dde-9b8c-95ddb0d7d89c
ms.openlocfilehash: e1251b6660db45f3af4f6e57114b1b10da18bd0a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73129862"
---
# <a name="corflagsexe-corflags-conversion-tool"></a>CorFlags.exe (Herramienta de conversión de CorFlags)
La herramienta de conversión CorFlags permite configurar la sección de CorFlags del encabezado de una imagen ejecutable portátil.  
  
 Esta herramienta se instala automáticamente con Visual Studio. Para ejecutar la herramienta, use Símbolo del sistema para desarrolladores de Visual Studio (o Símbolo del sistema de Visual Studio en Windows 7). Para más información, consulte [Símbolos del sistema](developer-command-prompt-for-vs.md).  
  
 En el símbolo del sistema, escriba lo siguiente:  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
CorFlags.exe assembly [options]  
```  
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro requerido|Description|  
|------------------------|-----------------|  
|`assembly`|El nombre del ensamblado para el que se va a configurar CorFlags.|  
  
|Opción|Description|  
|:------------|-----------------|  
|`-32BIT[REQ]+`|Establece la marca 32BITREQUIRED.|  
|`-32BIT[REQ]-`|Borra la marca 32BITREQUIRED.|  
|`-32BITPREF+`|Establece la marca 32BITPREFERRED. La aplicación se ejecuta como un proceso de 32 bits incluso en plataformas de 64 bits. Establezca esta marca únicamente en archivos EXE. Si la marca se establece en un archivo DLL, este genera un error al cargarse en procesos de 64 bits y se produce una excepción <xref:System.BadImageFormatException>. Los archivos EXE que tienen esta marca se pueden cargar en procesos de 64 bits.<br /><br /> Novedades de .NET Framework 4.5.|  
|`-32BITPREF-`|Borra la marca 32BITPREFERRED.<br /><br /> Novedades de .NET Framework 4.5.|  
|`-?`|Muestra las opciones y la sintaxis de los comandos para la herramienta.|  
|`-Force`|Fuerza una actualización aunque se trate de un ensamblado con nombre seguro. **Importante:** Si actualiza un ensamblado con nombre seguro, deberá volver a firmarlo antes de ejecutar su código.|  
|`-help`|Muestra las opciones y la sintaxis de los comandos para la herramienta.|  
|`-ILONLY+`|Establece la marca ILONLY.|  
|`-ILONLY-`|Borra la marca ILONLY.|  
|`-nologo`|Suprime la presentación de la portada de inicio de Microsoft.|  
|`-RevertCLRHeader`|Vuelve a establecer la versión del encabezado CLR en 2.0.|  
|`-UpgradeCLRHeader`|Actualiza la versión del encabezado CLR a la 2.5. **Nota:** Para que los ensamblados se ejecuten de forma nativa, la versión del encabezado CLR debe ser la 2.5 o posterior.|  
  
## <a name="remarks"></a>Comentarios  
 Si no se especifica ninguna opción, la herramienta de conversión CorFlags muestra las marcas para el ensamblado especificado.  
  
## <a name="see-also"></a>Vea también

- [Herramientas](index.md)
- [Aplicaciones de 64 bits](../64-bit-apps.md)
- [Símbolos del sistema](developer-command-prompt-for-vs.md)
