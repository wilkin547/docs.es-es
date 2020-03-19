---
title: TlbImp.exe (Importador de la biblioteca de tipos)
ms.date: 03/30/2017
helpviewer_keywords:
- type libraries [.NET Framework], importing
- importing type library
- Tlbimp.exe
- type definition conversion
- Type Library Importer
- type libraries
- converting type definitions
ms.assetid: ec0a8d63-11b3-4acd-b398-da1e37e97382
ms.openlocfilehash: d942378888b06049022188c75456f438d4b187e3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "79180240"
---
# <a name="tlbimpexe-type-library-importer"></a>TlbImp.exe (Importador de la biblioteca de tipos)
El Importador de la biblioteca de tipos convierte las definiciones de tipos encontradas en una biblioteca de tipos COM en las definiciones equivalentes en un ensamblado de Common Language Runtime. El resultado de Tlbimp.exe es un archivo binario (un ensamblado) que contiene los metadatos en tiempo de ejecución para los tipos definidos en la biblioteca de tipos original. Este archivo se puede examinar con herramientas como [Ildasm.exe](ildasm-exe-il-disassembler.md).  
  
 Esta herramienta se instala automáticamente con Visual Studio. Para ejecutar la herramienta, use Símbolo del sistema para desarrolladores de Visual Studio (o Símbolo del sistema de Visual Studio en Windows 7). Para más información, consulte [Símbolos del sistema](developer-command-prompt-for-vs.md).  
  
 En el símbolo del sistema, escriba lo siguiente:  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
tlbimp tlbFile [options]  
```  
  
## <a name="parameters"></a>Parámetros  
  
|Argumento|Descripción|  
|--------------|-----------------|  
|*tlbFile*|Nombre de cualquier archivo que contenga una biblioteca de tipos COM.|  
  
|Opción|Descripción|  
|------------|-----------------|  
|**/asmversion:** *versionnumber*|Especifica el número de versión del ensamblado que se genera. Especifique *númeroVersión* con el formato *principal.secundaria.compilación.revisión*.|  
|**/company:** `companyinformation`|Agrega información de la compañía al ensamblado de salida.|  
|**/copyright:** `copyrightinformation`|Agrega información de copyright al ensamblado de salida. Esta información se puede ver en el cuadro de diálogo **Propiedades del archivo** del ensamblado.|  
|**/delaysign**|Indica a la herramienta Tlbimp.exe que firme el ensamblado resultante con un nombre seguro mediante la firma retardada. Esta opción se debe especificar con las opciones **/keycontainer:** , **/keyfile:** o **/publickey:** . Para obtener más información sobre el proceso de firma retardada, vea [Retrasar la firma de un ensamblado](../../standard/assembly/delay-sign.md).|  
|**/help**|Muestra las opciones y la sintaxis de los comandos para la herramienta.|  
|**/keycontainer:** *containername*|Firma el ensamblado resultante con un nombre seguro utilizando el par de claves pública y privada que se encuentra en el contenedor de claves especificado mediante *nombreContenedor*.|  
|**/keyfile:** *filename*|Firma el ensamblado resultante con un nombre seguro utilizando el par de claves pública y privada oficial del editor que se encuentra en *nombreArchivo*.|  
|**/machine:** `machinetype`|Crea un ensamblado cuyo destino es el tipo de equipo especificado (microprocesador). Tipos de equipo compatibles: x86, x64, Itanium y Agnostic.|  
|**/namespace:** *namespace*|Especifica el espacio de nombres en que se genera el ensamblado.|  
|**/noclassmembers**|Evita que Tlbimp.exe agregue miembros a las clases. Esto evita una posible excepción <xref:System.TypeLoadException>.|  
|**/nologo**|Suprime la presentación de la portada de inicio de Microsoft.|  
|**/out:** *filename*|Especifica el nombre del archivo de salida, el ensamblado y el espacio de nombres en el que se escriben las definiciones de los metadatos. La opción **/out** no afecta al espacio de nombres del ensamblado si la biblioteca de tipos especifica el atributo personalizado de lenguaje de definición de interfaz (IDL) que controla explícitamente el espacio de nombres del ensamblado. Si no se especifica esta opción, Tlbimp.exe escribe los metadatos en un archivo con el mismo nombre que la biblioteca de tipos real definida en el archivo de entrada y le asigna una extensión .dll. Si el archivo de salida tiene el mismo nombre que el archivo de entrada, la herramienta genera un error para evitar que se sobrescriba la biblioteca de tipos.|  
|**/primary**|Genera un ensamblado de interoperabilidad primario para la biblioteca de tipos especificada. La información se agrega al ensamblado indicando que se ha generado con el editor de la biblioteca de tipos. Al especificar un ensamblado de interoperabilidad primario, es posible diferenciar el ensamblado de un editor de otros ensamblados creados desde la biblioteca de tipos mediante Tlbimp.exe. Solo debería utilizar la opción **/primary** si es el editor de la biblioteca de tipos que va a importar con Tlbimp.exe. Tenga en cuenta que debe firmar un ensamblado de interoperabilidad primario con un [nombre seguro](../../standard/assembly/strong-named.md). Para obtener más información, vea [Ensamblados de interoperabilidad primarios](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aax7sdch(v=vs.100)).|  
|**/product:** `productinformation`|Agrega información del producto al ensamblado de salida. Esta información se puede ver en el cuadro de diálogo **Propiedades del archivo** del ensamblado.|  
|**/productversion:** `productversioninformation`|Agrega información de la versión al ensamblado de salida. No hay restricciones de formato. Esta información se puede ver en el cuadro de diálogo **Propiedades del archivo** del ensamblado.|  
|**/publickey:** *filename*|Especifica el archivo que contiene la clave pública que se va a utilizar para firmar el ensamblado resultante. Si se especifica las opciones **/keyfile:** o **/keycontainer:** en lugar de **/publickey:** , Tlbimp.exe genera la clave pública a partir del par de claves pública y privada suministrado por **/keyfile:** o **/keycontainer:** . La opción **/publickey:** admite los escenarios de clave de prueba y de firma retardada. El archivo tiene el formato generado por Sn.exe. Para obtener más información, vea la opción **-p** de Sn.exe en la [herramienta Nombre seguro (Sn.exe)](sn-exe-strong-name-tool.md).|  
|**/reference:** *filename*|Especifica el archivo de ensamblado que se utiliza para resolver referencias en tipos definidos fuera de la biblioteca de tipos actual. Si no se especifica la opción **/reference**, Tlbimp.exe importa de forma automática y recursiva todas las bibliotecas de tipos externas a la que se haga referencia en la biblioteca de tipos que se va a importar. Si especifica la opción **/reference**, la herramienta intenta resolver los tipos externos en los ensamblados a los que se hace referencia antes de importar otras bibliotecas de tipos.|  
|**/silence:** `warningnumber`|Suprime la presentación de la advertencia especificada. Esta opción no se puede utilizar con la opción **/silent**.|  
|**/silent**|Suprime la presentación de mensajes de aprobación. Esta opción no se puede utilizar con la opción **/silence**.|  
|**/strictref**|No importa una biblioteca de tipos si la herramienta no puede resolver todas las referencias dentro del ensamblado actual, los ensamblados especificados con la opción **/reference** o los ensamblados de interoperabilidad primarios (PIA) registrados.|  
|**/strictref:nopia**|Igual que **/strictref**, pero omite los PIA.|  
|**/sysarray**|Indica a la herramienta que importe una matriz SafeArray de estilos COM como un tipo <xref:System.Array> administrado.|  
|**/tlbreference:** *filename*|Especifica el archivo de la biblioteca de tipos que se debe utilizar para resolver las referencias de la biblioteca de tipos sin consultar el Registro.<br /><br /> Observe que esta opción no cargará algunos de los formatos de la biblioteca de tipos más antiguos.  Sin embargo, todavía puede cargarlos de forma implícita a través del Registro o del directorio actual.|  
|**/trademark:** `trademarkinformation`|Agrega información de marca comercial al ensamblado de salida. Esta información se puede ver en el cuadro de diálogo **Propiedades del archivo** del ensamblado.|  
|**/transform:** *transformname*|Transforma los metadatos tal y como especifica el parámetro *nombreTransformación*.<br /><br /> Especifique **dispret** para que el parámetro *nombreTransformación* transforme los parámetros [out, retval] de los métodos de las interfaces de solo envío (interfaces dispinterface) en valores devueltos.<br /><br /> Para obtener más información sobre esta opción, vea los ejemplos que se muestran más adelante en este tema.|  
|**/unsafe**|Genera interfaces sin comprobaciones de seguridad de .NET Framework. La llamada a un método que se expone de esta forma puede poner en riesgo la seguridad. Esta opción no se debe utilizar a no ser que se conozcan los riesgos que supone exponer este código.|  
|**/verbose**|Especifica el modo detallado; muestra información adicional sobre la biblioteca de tipos importada.|  
|**/VariantBoolFieldToBool**|Convierte los campos `VARIANT_BOOL` de las estructuras en <xref:System.Boolean>.|  
|**/?**|Muestra las opciones y la sintaxis de los comandos para la herramienta.|  
  
> [!NOTE]
> Las opciones de la línea de comandos de Tlbimp.exe no distinguen entre mayúsculas y minúsculas, y se pueden proporcionar en cualquier orden. Por otra parte, basta con especificar parte de la opción de forma que se identifique de manera inequívoca. Por lo tanto, **/n** equivale a **/nologo** y **/ou:** *outfile.dll* equivale a **/out:** *outfile.dll*.  
  
## <a name="remarks"></a>Comentarios  
 Tlbimp.exe realiza las conversiones de una biblioteca completa de tipos de una vez. No se puede utilizar esta herramienta para generar información de tipos para un subconjunto de los tipos definidos en una biblioteca de tipos sencilla.  
  
 Hay veces que resulta útil o es necesario poder asignar [nombres seguros](../../standard/assembly/strong-named.md) a los ensamblados. Por consiguiente, Tlbimp.exe incluye opciones que proporcionan la información necesaria para generar ensamblados con nombre seguro. Las dos opciones **/keyfile:** y **/keycontainer:** firman los ensamblados con nombres seguros. Por tanto, lo lógico es proporcionar una de estas opciones cada vez.  
  
 Puede especificar diversos ensamblados de referencia utilizando la opción **/reference** varias veces.

 Debido a la forma en que Tlbimp.exe genera ensamblados, no es posible redirigir a un ensamblado a otra versión de `mscorlib`. Por ejemplo, si desea generar un ensamblado que tiene como destino .NET Framework 2.0, será necesario usar la versión de Tlbimp.exe incluida en el SDK de .NET Framework 2.0/3.0/3.5. Para usar .NET Framework 4.x como destino, será necesario usar la versión de Tlbimp.exe incluida con el SDK de .NET Framework 4.x.

 De manera opcional, un identificador de recurso se puede anexar a un archivo de biblioteca de tipos cuando se importa desde un módulo que contiene varias bibliotecas de tipos. Tlbimp.exe encuentra este archivo solo si se ubica en el directorio actual o si se especifica la ruta de acceso completa. Vea el ejemplo que se muestra más adelante en este tema.  
  
## <a name="examples"></a>Ejemplos  
 El comando siguiente genera un ensamblado con el mismo nombre que el de la biblioteca de tipos que se encuentra en `myTest.tlb` y con la extensión .dll.  
  
```console  
tlbimp myTest.tlb
```  
  
 El comando siguiente genera un ensamblado con el nombre `myTest.dll`.  
  
```console  
tlbimp  myTest.tlb  /out:myTest.dll  
```  
  
 El comando siguiente genera un ensamblado con el mismo nombre que la biblioteca de tipos especificada por `MyModule.dll\1` y con la extensión .dll. `MyModule.dll\1` debe estar ubicado en el directorio actual.  
  
```console  
tlbimp MyModule.dll\1  
```  
  
 El comando siguiente genera un ensamblado con el nombre `myTestLib.dll` para la biblioteca de tipos `TestLib.dll`. La opción **/transform:dispret** transforma los parámetros [out, retval] de los métodos de las interfaces dispinterface de la biblioteca de tipos en valores devueltos de la biblioteca administrada.  
  
```console  
tlbimp TestLib.dll /transform:dispret /out:myTestLib.dll  
```  
  
 En el ejemplo anterior, la biblioteca de tipos `TestLib.dll` incluye un método de interfaz dispinterface denominado `SomeMethod` que devuelve void y que tiene un parámetro [out, retval]. El siguiente código es la signatura del método de la biblioteca de tipos de entrada de `SomeMethod` en `TestLib.dll`.  
  
```cpp  
void SomeMethod([out, retval] VARIANT_BOOL*);  
```  
  
 Al especificar la opción **/transform:dispret**, Tlbimp.exe transforma el parámetro `[out, retval]` de `SomeMethod` en un valor devuelto de tipo `bool`. A continuación, se muestra la signatura del método que Tlbimp.exe genera para `SomeMethod` en la biblioteca administrada `myTestLib.dll` cuando se especifica la opción **/transform:dispret**.  
  
```csharp  
bool SomeMethod();  
```  
  
 Si utiliza Tlbimp.exe para generar una biblioteca administrada para `TestLib.dll` sin especificar la opción **/transform:dispret**, la herramienta genera la siguiente signatura de método para `SomeMethod` en la biblioteca administrada `myTestLib.dll`.  
  
```csharp  
void SomeMethod(out bool x);  
```  
  
## <a name="see-also"></a>Vea también

- [Herramientas](index.md)
- [Tlbexp.exe (Exportador de la biblioteca de tipos)](tlbexp-exe-type-library-exporter.md)
- [Importar una biblioteca de tipos como un ensamblado](../interop/importing-a-type-library-as-an-assembly.md)
- [Resumen de la conversión de bibliotecas de tipos en ensamblados](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100))
- [Ildasm.exe (Desensamblador de IL)](ildasm-exe-il-disassembler.md)
- [Sn.exe (Herramienta de nombre seguro)](sn-exe-strong-name-tool.md)
- [Ensamblados con nombre seguro](../../standard/assembly/strong-named.md)
- [Atributos para importar bibliotecas de tipos en ensamblados de interoperabilidad](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/y6a7ak23(v=vs.100))
- [Símbolos del sistema](developer-command-prompt-for-vs.md)
