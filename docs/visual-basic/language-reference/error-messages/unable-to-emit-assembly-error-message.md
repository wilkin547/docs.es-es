---
title: 'No se puede emitir el ensamblado: <error message>'
ms.date: 08/14/2018
f1_keywords:
- vbc30145
- bc30145
helpviewer_keywords:
- BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
ms.openlocfilehash: 012284aa42dfa29ad1a5e4ec4a4df5eaacbd4fb7
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65642280"
---
# <a name="unable-to-emit-assembly-error-message"></a>No se puede emitir el ensamblado: \<mensaje de error >

El compilador de Visual Basic llama a Assembly Linker (*Al.exe*, también conocido como Alink) generar un ensamblado con un manifiesto y el vinculador informa de un error en la fase de emisión de creación del ensamblado.

**Identificador de error:** BC30145

## <a name="to-correct-this-error"></a>Para corregir este error

1. Examine el mensaje de error citado y consulte el tema [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) para obtener más información y consejos.

2. Intente firmar el ensamblado manualmente, mediante la [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) o [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md).

3. Si el error persiste, reúna información sobre las circunstancias y notifíquelo a los Servicios de soporte técnico de Microsoft.

### <a name="to-sign-the-assembly-manually"></a>Para firmar el ensamblado manualmente

1. Utilice la [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)) para crear un archivo de par de claves pública y privada.

   Este archivo tiene un *.snk* extensión.

2. Elimine la referencia COM que está provocando el error en el proyecto.

3. Abra el [símbolo del sistema para desarrolladores de Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md).

   En Windows 10, escriba **símbolo** en el cuadro de búsqueda en la barra de tareas. A continuación, seleccione **símbolo del sistema para desarrolladores para VS 2017** desde la lista de resultados.

4. Cambie el directorio al directorio donde desea colocar el contenedor de ensamblado.

5. Escriba el comando siguiente:

    ```cmd
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>
    ```

   Es un ejemplo del comando real que podría escribir:

    ```cmd
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"
    ```

   > [!TIP]
   > Si un archivo o ruta de acceso contiene espacios, utilice comillas dobles.

6. En Visual Studio, agregue una referencia de ensamblado .NET al archivo que acaba de crear.

## <a name="see-also"></a>Vea también

- [Al.exe](../../../framework/tools/al-exe-assembly-linker.md)
- [Sn.exe (Herramienta de nombre seguro)](../../../framework/tools/sn-exe-strong-name-tool.md)
- [Cómo: Creación de un par de claves privada y pública](../../../framework/app-domains/how-to-create-a-public-private-key-pair.md)
- [Hable con nosotros](/visualstudio/ide/talk-to-us)
