---
title: 'Cómo: Escribir texto en archivos del directorio Mis documentos'
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], writing to
- text, writing to files
- examples [Visual Basic], text files
- writing to files [Visual Basic], in My Documents
ms.assetid: 1c726124-781d-4976-9baa-ed46814ff3fe
ms.openlocfilehash: bb3a9bdc44f86fbcdb3c56ee088740efdfebe95d
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546463"
---
# <a name="how-to-write-text-to-files-in-the-my-documents-directory-in-visual-basic"></a>Cómo: Escribir texto en archivos del directorio Mis documentos en Visual Basic

El objeto `My.Computer.FileSystem.SpecialDirectories` le permite tener acceso a los directorios especiales, como el directorio **MyDocuments**.  
  
## <a name="procedure"></a>Procedimiento  
  
#### <a name="to-write-new-text-files-in-the-my-documents-directory"></a>Para escribir nuevos archivos de texto en el directorio Mis documentos  
  
1. Use la propiedad `My.Computer.FileSystem.SpecialDirectories.MyDocuments` para proporcionar la ruta de acceso.  
  
     [!code-vb[VbFileIOWrite#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOWrite/VB/Class1.vb#1)]  
  
2. Use el método `WriteAllText` para escribir texto en el archivo especificado.  
  
     [!code-vb[VbVbcnMyFileSystem#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#14)]  
  
## <a name="example"></a>Ejemplo  

 [!code-vb[VbFileIOWrite#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOWrite/VB/Class1.vb#2)]  
  
## <a name="compiling-the-code"></a>Compilar el código  

 Reemplace `test.txt` por el nombre del archivo en el que quiere escribir.  
  
## <a name="robust-programming"></a>Programación sólida  

 Este código vuelve a producir todas las excepciones que pueden ocurrir al escribir texto en el archivo. Puede reducir la probabilidad de que se produzcan excepciones usando los controles de Windows Forms como los componentes [OpenFileDialog](/dotnet/desktop/winforms/controls/openfiledialog-component-windows-forms) y [SaveFileDialog](/dotnet/desktop/winforms/controls/savefiledialog-component-windows-forms), que limitan las opciones del usuario a los nombres de archivo válidos. En cambio, el uso de estos controles no es infalible. El sistema de archivos puede cambiar entre el momento en el que el usuario selecciona un archivo y el momento en el que se ejecuta el código. Por ello, cuando se trabaja con archivos casi siempre es prácticamente necesario realizar un control de excepciones.  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  

 Si realiza una ejecución en un contexto de confianza parcial, el código podría desencadenar una excepción por falta de privilegios. Para obtener más información, vea [Code Access Security Basics](../../../../framework/misc/code-access-security-basics.md) (Aspectos básicos de seguridad de acceso del código).  
  
 En este ejemplo se crea un nuevo archivo. Si una aplicación necesita crear un archivo, precisará permisos de creación para la carpeta correspondiente. Los permisos se establecen usando listas de control de acceso. Si el archivo ya existe, la aplicación solo necesitará permiso de escritura, un privilegio menor. Siempre que sea posible, resulta más seguro crear el archivo durante la implementación y conceder solo privilegios de lectura en un solo archivo, en lugar de privilegios de creación para una carpeta. También es más seguro escribir datos en carpetas de usuario en lugar de en la carpeta raíz o en la carpeta **Archivos de programa**. Para obtener más información, vea [Información general sobre la tecnología ACL](/previous-versions/dotnet/netframework-4.0/ms229742(v=vs.100)).  
  
## <a name="see-also"></a>Vea también

- <xref:System.IO.Path.Combine%2A?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>
- <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>
