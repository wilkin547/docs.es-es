---
title: -keyfile
ms.date: 03/10/2018
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
ms.openlocfilehash: 2617c42d7b176806cfac0fc2247760727608261a
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775639"
---
# <a name="-keyfile"></a>-keyfile
Especifica un archivo que contiene una clave o un par de claves que asigna un nombre seguro al ensamblado.  
  
## <a name="syntax"></a>Sintaxis  
  
```console 
-keyfile:file  
```  
  
## <a name="arguments"></a>Argumentos  
 `file`  
 Requerido. Archivo que contiene la clave. Si el nombre de archivo contiene un espacio, incluya el nombre entre comillas ("").  
  
## <a name="remarks"></a>Comentarios  
 El compilador inserta la clave pública en el manifiesto del ensamblado y, a continuación, firma el ensamblado final con la clave privada. Para generar un archivo de claves, escriba `sn -k file` en la línea de comandos. Para obtener más información, consulte [SN. exe (herramienta de nombre seguro)](../../../framework/tools/sn-exe-strong-name-tool.md)).  
  
 Si compila con `-target:module`, el nombre del archivo de clave se mantiene en el módulo y se incorpora en el ensamblado que se crea al compilar un ensamblado con [-AddModule](../../../visual-basic/reference/command-line-compiler/addmodule.md).  
  
 También puede pasar la información de cifrado al compilador con [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md). Use [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) para firmar el ensamblado de forma parcial.  
  
 También puede especificar esta opción como un atributo personalizado (<xref:System.Reflection.AssemblyKeyFileAttribute>) en el código fuente de cualquier módulo de lenguaje intermedio de Microsoft.  
  
 En caso de que se especifiquen `-keyfile` y [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) (ya sea mediante la opción de línea de comandos o mediante un atributo personalizado) en la misma compilación, el compilador primero intentará el contenedor de claves. Si lo consigue, el ensamblado se firma con la información del contenedor de claves. Si el compilador no encuentra el contenedor de claves, intenta el archivo especificado con `-keyfile`. Si esto se realiza correctamente, el ensamblado se firma con la información del archivo de clave y la información de clave se instala en el contenedor de claves (similar a `sn -i`) para que en la siguiente compilación, el contenedor de claves sea válido.  
  
 Tenga en cuenta que un archivo de clave puede contener solo la clave pública.  
  
 Vea [crear y utilizar ensamblados con nombre seguro](../../../standard/assembly/create-use-strong-named.md) para obtener más información sobre la firma de un ensamblado.  
  
> [!NOTE]
> La opción `-keyfile` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible al compilar desde la línea de comandos.

## <a name="example"></a>Ejemplo

El código siguiente compila el archivo de código fuente `Input.vb` y especifica un archivo de clave.

```console
vbc -keyfile:myfile.sn input.vb
```

## <a name="see-also"></a>Vea también

- [Ensamblados de .NET](../../../standard/assembly/index.md)
- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
