---
title: -keycontainer
ms.date: 03/10/2018
helpviewer_keywords:
- -keycontainer compiler option [Visual Basic]
- keycontainer compiler option [Visual Basic]
- /keycontainer compiler option [Visual Basic]
ms.assetid: 6a9bc861-1752-4db1-9f64-b5252f0482cc
ms.openlocfilehash: 243583e55dcf278f951b813cca8384246d2d6db9
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91085235"
---
# <a name="-keycontainer"></a>-keycontainer

Especifica un nombre de contenedor de claves para un par de claves que asigna un nombre seguro al ensamblado.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-keycontainer:container  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`container`|Obligatorio. Archivo contenedor que contiene la clave. Si el nombre de archivo contiene un espacio, escríbalo entre comillas (" ").|  
  
## <a name="remarks"></a>Comentarios  

 El compilador crea un componente compartible mediante la inserción de una clave pública en el manifiesto del ensamblado y la firma del ensamblado final con la clave privada. Para generar un archivo de claves, escriba `sn -k file` en la línea de comandos. La opción `-i` instala el par de claves en un contenedor. Para obtener más información, vea [Sn.exe (herramienta de nombre seguro)](../../../framework/tools/sn-exe-strong-name-tool.md).  
  
 Si se compila con `-target:module`, el nombre del archivo de claves se mantiene en el módulo y se incorpora al ensamblado que se crea al compilar un ensamblado con [-addmodule](addmodule.md).  
  
 También se puede especificar esta opción como un atributo personalizado (<xref:System.Reflection.AssemblyKeyNameAttribute>) en el código fuente de cualquier módulo del Lenguaje Intermedio de Microsoft (MSIL).  
  
 También se puede pasar la información de cifrado al compilador con [-keyfile](keyfile.md). Use [-delaysign](delaysign.md) para firmar el ensamblado de forma parcial.  
  
 Para obtener más información sobre cómo firmar un ensamblado, vea [Creación y uso de ensamblados con nombre seguro](../../../standard/assembly/create-use-strong-named.md).  
  
> [!NOTE]
> La opción `-keycontainer` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde la línea de comandos.  
  
## <a name="example"></a>Ejemplo  

 En el código siguiente se compila el archivo de código fuente `Input.vb` y se especifica un contenedor de claves.  
  
```console  
vbc -keycontainer:key1 input.vb  
```  
  
## <a name="see-also"></a>Vea también

- [Ensamblados de .NET](../../../standard/assembly/index.md)
- [Compilador de línea de comandos de Visual Basic](index.md)
- [-keyfile](keyfile.md)
- [Líneas de comandos de compilación de ejemplo](sample-compilation-command-lines.md)
