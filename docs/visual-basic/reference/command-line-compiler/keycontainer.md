---
title: -keycontainer
ms.date: 03/10/2018
helpviewer_keywords:
- -keycontainer compiler option [Visual Basic]
- keycontainer compiler option [Visual Basic]
- /keycontainer compiler option [Visual Basic]
ms.assetid: 6a9bc861-1752-4db1-9f64-b5252f0482cc
ms.openlocfilehash: be2ad1416e801398fb513593c7f3828e5488bfaf
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005529"
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
|`container`|Obligatorio. Archivo contenedor que contiene la clave. Escriba el nombre de archivo entre comillas ("") si el nombre contiene un espacio.|  
  
## <a name="remarks"></a>Comentarios  
 El compilador crea el componente compartible insertando una clave pública en el manifiesto del ensamblado y firma el ensamblado final con la clave privada. Para generar un archivo de claves, escriba `sn -k file` en la línea de comandos. La opción `-i` instala el par de claves en un contenedor. Para obtener más información, consulte [SN. exe (herramienta de nombre seguro)](../../../framework/tools/sn-exe-strong-name-tool.md)).  
  
 Si compila con `-target:module`, el nombre del archivo de clave se mantiene en el módulo y se incorpora en el ensamblado que se crea al compilar un ensamblado con [-AddModule](../../../visual-basic/reference/command-line-compiler/addmodule.md).  
  
 También se puede especificar esta opción como un atributo personalizado (<xref:System.Reflection.AssemblyKeyNameAttribute>) en el código fuente de cualquier módulo del Lenguaje Intermedio de Microsoft (MSIL).  
  
 También se puede pasar la información de cifrado al compilador con [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md). Use [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) para firmar el ensamblado de forma parcial.  
  
 Vea [crear y utilizar ensamblados con nombre seguro](../../../standard/assembly/create-use-strong-named.md) para obtener más información sobre la firma de un ensamblado.  
  
> [!NOTE]
> La opción `-keycontainer` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible al compilar desde la línea de comandos.  
  
## <a name="example"></a>Ejemplo  
 En el código siguiente se compila el archivo de código fuente `Input.vb` y se especifica un contenedor de claves.  
  
```console  
vbc -keycontainer:key1 input.vb  
```  
  
## <a name="see-also"></a>Vea también

- [Ensamblados de .NET](../../../standard/assembly/index.md)
- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
