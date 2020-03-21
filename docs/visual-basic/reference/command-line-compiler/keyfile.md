---
title: -keyfile
ms.date: 03/10/2018
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
ms.openlocfilehash: cffc3c5f0ff3dd48ca2c74bde346a967b209dc5f
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266747"
---
# <a name="-keyfile"></a>-keyfile
Especifica un archivo que contiene una clave o un par de claves que asigna un nombre seguro al ensamblado.  
  
## <a name="syntax"></a>Sintaxis  
  
```console
-keyfile:file  
```  
  
## <a name="arguments"></a>Argumentos  
 `file`  
 Necesario. Archivo que contiene la clave. Si el nombre de archivo contiene un espacio, escriba el nombre entre comillas (" ").  
  
## <a name="remarks"></a>Observaciones  
 El compilador inserta la clave pública en el manifiesto del ensamblado y, a continuación, firma el ensamblado final con la clave privada. Para generar un archivo de claves, escriba `sn -k file` en la línea de comandos. Para obtener más información, vea [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)).  
  
 Si compila `-target:module`con , el nombre del archivo de claves se mantiene en el módulo y se incorpora al ensamblado que se crea al compilar un ensamblado con [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).  
  
 También puede pasar la información de cifrado al compilador con [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md). Use [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) para firmar el ensamblado de forma parcial.  
  
 También puede especificar esta opción como<xref:System.Reflection.AssemblyKeyFileAttribute>un atributo personalizado ( ) en el código fuente para cualquier módulo de lenguaje intermedio de Microsoft.  
  
 En caso `-keyfile` de que se especifiquen ambos y [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) (ya sea por opción de línea de comandos o por atributo personalizado) en la misma compilación, el compilador primero intenta el contenedor de claves. Si lo consigue, el ensamblado se firma con la información del contenedor de claves. Si el compilador no encuentra el contenedor de claves, intenta el archivo especificado con `-keyfile`. Si esto se realiza correctamente, el ensamblado se firma con la información del archivo de `sn -i`claves y la información de clave se instala en el contenedor de claves (similar a ) para que en la siguiente compilación, el contenedor de claves será válido.  
  
 Tenga en cuenta que un archivo de clave puede contener solo la clave pública.  
  
 Consulte [Creación y uso de ensamblados con nombre seguro](../../../standard/assembly/create-use-strong-named.md) para obtener más información sobre la firma de un ensamblado.  
  
> [!NOTE]
> La `-keyfile` opción no está disponible en el entorno de desarrollo de Visual Studio; sólo está disponible cuando se compila desde la línea de comandos.

## <a name="example"></a>Ejemplo

El código siguiente compila `Input.vb` el archivo de código fuente y especifica un archivo de clave.

```console
vbc -keyfile:myfile.sn input.vb
```

## <a name="see-also"></a>Consulte también

- [Ensamblados de .NET](../../../standard/assembly/index.md)
- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-referencia (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
