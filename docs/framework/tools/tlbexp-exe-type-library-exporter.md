---
title: Tlbexp.exe (Exportador de la biblioteca de tipos)
description: Revise Tlbexp.exe, el Exportador de la biblioteca de tipos. Esta herramienta genera una biblioteca de tipos que describe los tipos definidos en un ensamblado de Common Language Runtime (CLR).
ms.date: 03/30/2017
helpviewer_keywords:
- exporting type library [.NET Framework]
- exporter tool [.NET Framework]
- Tlbexp.exe
- Type Library Exporter
- type libraries [.NET Framework], exporting
ms.assetid: a487d61b-d166-467b-a7ca-d8b52fbff42d
ms.openlocfilehash: 1a9e984e1b81adda572076cb118a25f5f3a045ea
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96283762"
---
# <a name="tlbexpexe-type-library-exporter"></a>Tlbexp.exe (Exportador de la biblioteca de tipos)

El Exportador de la biblioteca de tipos genera una biblioteca que describe los tipos definidos en un ensamblado de Common Language Runtime.  
  
 Esta herramienta se instala automáticamente con Visual Studio. Para ejecutar la herramienta, use Símbolo del sistema para desarrolladores de Visual Studio (o Símbolo del sistema de Visual Studio en Windows 7). Para más información, consulte [Símbolos del sistema](developer-command-prompt-for-vs.md).  
  
 En el símbolo del sistema, escriba lo siguiente:  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
tlbexp assemblyName [options]  
```  
  
## <a name="parameters"></a>Parámetros  
  
|Argumento|Descripción|  
|--------------|-----------------|  
|*assemblyName*|Ensamblado para el que se exporta una biblioteca de tipos.|  
  
|Opción|Descripción|  
|------------|-----------------|  
|**/asmpath:** *directory*|Especifica la ubicación en la que buscar los ensamblados. Si utiliza esta opción, debe especificar de forma explícita las ubicaciones en las que desea buscar los ensamblados a los que se hace referencia, incluido el directorio actual.<br /><br /> Cuando se usa la opción **asmpath**, el Exportador de la biblioteca de tipos no busca ensamblados en la caché global de ensamblados (GAC).|  
|**/help**|Muestra las opciones y la sintaxis de los comandos para la herramienta.|  
|**/names:** *filename*|Especifica el uso de mayúsculas y minúsculas en los nombres de una biblioteca de tipos. El argumento *nombreDeArchivo* es un archivo de texto. Cada línea del archivo especifica el uso de mayúsculas y minúsculas en un nombre de la biblioteca de tipos.|  
|**/nologo**|Suprime la presentación de la portada de inicio de Microsoft.|  
|**/oldnames**|Fuerza a Tlbexp.exe a exportar los nombres de los tipos representativos si existe un conflicto de nombres de tipos. Tenga en cuenta que este era el comportamiento predeterminado en versiones anteriores a la versión 2.0 de .NET Framework.|  
|**/out:** *file*|Especifica el nombre del archivo de biblioteca de tipos que se genera. Si se omite esta opción, Tlbexp.exe genera una biblioteca de tipos con el mismo nombre que el ensamblado (el nombre real del ensamblado, que no tiene por qué coincidir necesariamente con el del archivo que lo contiene) y una extensión .tlb.|  
|**/silence:** `warningnumber`|Suprime la presentación de la advertencia especificada. Esta opción no se puede utilizar con la opción **/silent**.|  
|**/silent**|Suprime la presentación de mensajes de aprobación. Esta opción no se puede utilizar con la opción **/silence**.|  
|**/tlbreference:** *typelibraryname*|Fuerza a Tlbexp.exe a resolver de forma explícita las referencias a bibliotecas de tipos sin consultar el Registro. Por ejemplo, si el ensamblado B hace referencia al ensamblado A, puede utilizar esta opción para proporcionar una referencia explícita a la biblioteca de tipos, en lugar de confiar en la biblioteca de tipos especificada en el Registro. Tlbexp.exe realiza una comprobación de la versión para asegurarse de que la versión de la biblioteca de tipos coincide con la del ensamblado; de lo contrario, genera un error.<br /><br /> Observe que la opción **tlbreference** sigue consultado el Registro en los casos en los que se aplica el atributo <xref:System.Runtime.InteropServices.ComImportAttribute> a una interfaz que otro tipo implementa posteriormente.|  
|**/tlbrefpath:** *path*|Ruta de acceso completa a una biblioteca de tipos a la que se hace referencia.|  
|**/win32**|Al realizar la compilación en un equipo de 64 bits, esta opción especifica que Tlbexp.exe debe generar una biblioteca de tipos de 32 bits.|  
|**/win64**|Al realizar la compilación en un equipo de 32 bits, esta opción especifica que Tlbexp.exe debe generar una biblioteca de tipos de 64 bits.|  
|**/verbose**|Especifica el modo detallado; muestra una lista de los ensamblados relacionados para los que es necesario generar una biblioteca de tipos.|  
|**/?**|Muestra las opciones y la sintaxis de los comandos para la herramienta.|  
  
> [!NOTE]
> Las opciones de la línea de comandos de Tlbexp.exe no distinguen entre mayúsculas y minúsculas, y se pueden proporcionar en cualquier orden. Por otra parte, basta con especificar parte de la opción de forma que se identifique de manera inequívoca. Por ejemplo, **/n** equivale a **/nologo** y **/o:** *outfile.tlb*, a **/out:** *outfile.tlb*.  
  
## <a name="remarks"></a>Comentarios  

 Tlbexp.exe genera una biblioteca de tipos que contiene las definiciones de los tipos definidos en el ensamblado. Las aplicaciones como Visual Basic 6.0 pueden utilizar la biblioteca de tipos generada para enlazarla a los tipos de .NET definidos en el ensamblado.  
  
> [!IMPORTANT]
> No puede utilizar Tlbexp.exe para exportar archivos de metadatos de Windows (.winmd). No se admite la exportación de ensamblados de Windows en tiempo de ejecución.  
  
 Todo el ensamblado se convierte de una vez. No se puede utilizar Tlbexp.exe para generar información de tipos correspondiente a un subconjunto de los tipos definidos en un ensamblado.  
  
 No se puede usar Tlbexp.exe para generar una biblioteca de tipos desde un ensamblado importado mediante el [Importador de la biblioteca de tipos (Tlbimp.exe)](tlbimp-exe-type-library-importer.md). En su lugar, debe hacer referencia a la biblioteca de tipos original que se importó con Tlbimp.exe. Puede exportar una biblioteca de tipos de un ensamblado que haga referencia a los ensamblados que se importaron mediante Tlbimp.exe. Consulte los ejemplos en la sección siguiente.  
  
 Tlbexp.exe coloca las bibliotecas de tipos generadas en el directorio de trabajo actual o en el directorio especificado para el archivo de salida. Un solo ensamblado puede generar varias bibliotecas de tipos.  
  
 Tlbexp.exe genera una biblioteca de tipos pero no la registra, a diferencia de la [herramienta Registro de ensamblados (Regasm.exe)](regasm-exe-assembly-registration-tool.md) que genera y registra una biblioteca de tipos. Para generar y registrar una biblioteca de tipos con COM, utilice Regasm.exe.  
  
 Si no especifica ni la opción `/win32` ni la opción `/win64`, Tlbexp.exe genera una biblioteca de tipos de 32 o de 64 bits, dependiendo del tipo de equipo en el que se está realizando la compilación (equipo de 32 bits o de 64 bits). Si desea realizar la compilación en diferentes plataformas, puede utilizar la opción `/win64` en un equipo de 32 bits para generar una biblioteca de tipos de 64 bits y la opción `/win32` en un equipo de 64 bits para generar una biblioteca de tipos de 32 bits. En las bibliotecas de tipos de 32 bits, el valor <xref:System.Runtime.InteropServices.ComTypes.SYSKIND> se establece en <xref:System.Runtime.InteropServices.ComTypes.SYSKIND.SYS_WIN32>. En las bibliotecas de tipos de 64 bits, el valor <xref:System.Runtime.InteropServices.ComTypes.SYSKIND> se establece en <xref:System.Runtime.InteropServices.ComTypes.SYSKIND.SYS_WIN64>. Todas las transformaciones de tipos de datos (por ejemplo, los tipos de datos de tamaño de puntero, como `IntPtr` y `UIntPtr`) se convierten correctamente.  
  
 Si utiliza el atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> para especificar un valor <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArraySubType> de `VT_UNKOWN` o `VT_DISPATCH`, Tlbexp.exe omite cualquier uso subsiguiente del campo <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArrayUserDefinedSubType>. Por ejemplo, dadas las siguientes signaturas:  
  
```csharp
[return:MarshalAs(UnmanagedType.SafeArray, SafeArraySubType=VarEnum.VT_UNKNOWN, SafeArrayUserDefinedSubType=typeof(ConsoleKeyInfo))] public Array StructUnkSafe(){return null;}  
[return:MarshalAs(UnmanagedType.SafeArray, SafeArraySubType=VarEnum.VT_DISPATCH, SafeArrayUserDefinedSubType=typeof(ConsoleKeyInfo))] public Array StructDispSafe(){return null;}  
```  
  
 se genera la biblioteca de tipos siguiente:  
  
```cpp
[id(0x60020004)]  
HRESULT StructUnkSafe([out, retval] SAFEARRAY(IUnknown*)* pRetVal);  
[id(0x60020005)]  
HRESULT StructDispSafe([out, retval] SAFEARRAY(IDispatch*)* pRetVal);  
```  
  
 Tenga en cuenta que Tlbexp.exe omite el campo <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArrayUserDefinedSubType>.  
  
 Como las bibliotecas de tipos no pueden dar cabida a toda la información que se encuentra en los ensamblados, Tlbexp.exe descarta algunos datos durante el proceso de exportación. Para obtener una explicación del proceso de transformación y de la identificación del origen de cada sección de información que se emite a una biblioteca de tipos, vea el [Resumen de la conversión de ensamblados en bibliotecas de tipos](/previous-versions/dotnet/netframework-4.0/xk1120c3(v=vs.100)).  
  
 Tenga en cuenta que el Exportador de la biblioteca de tipos exporta métodos que tienen parámetros <xref:System.TypedReference> como `VARIANT`, incluso si el objeto <xref:System.TypedReference> no tiene ningún significado en el código no administrado. Cuando se exportan métodos que tengan parámetros <xref:System.TypedReference>, el Exportador de la biblioteca de tipos no genera ninguna advertencia ni error, y el código no administrado que utiliza la biblioteca de tipos resultante no se ejecuta correctamente.  
  
 El Exportador de la biblioteca de tipos se admite en Microsoft Windows 2000 y versiones posteriores.  
  
## <a name="examples"></a>Ejemplos  

 El comando siguiente genera una biblioteca de tipos con el mismo nombre que el ensamblado que se encuentra en `myTest.dll`.  
  
```console  
tlbexp myTest.dll  
```  
  
 El comando siguiente genera una biblioteca de tipos con el nombre `clipper.tlb`.  
  
```console  
tlbexp myTest.dll /out:clipper.tlb  
```  
  
 El ejemplo siguiente muestra el uso de Tlbexp.exe para exportar una biblioteca de tipos desde un ensamblado que hace referencia a ensamblados que se importaron con Tlbimp.exe.  
  
 Primero se utiliza Tlbimp.exe para importar la biblioteca de tipos `myLib.tlb` y guardarla como `myLib.dll`.  
  
```console  
tlbimp myLib.tlb /out:myLib.dll  
```  
  
 En el siguiente comando se usa el compilador de C# para compilar el archivo `Sample.dll,` que hace referencia al archivo `myLib.dll` creado en el ejemplo anterior.  
  
```console  
CSC Sample.cs /reference:myLib.dll /out:Sample.dll  
```  
  
 El comando siguiente genera una biblioteca de tipos para `Sample.dll` que hace referencia a `myLib.dll`.  
  
```console  
tlbexp Sample.dll  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.InteropServices.TypeLibExporterFlags>
- [Herramientas](index.md)
- [Regasm.exe (Herramienta de registro de ensamblados)](regasm-exe-assembly-registration-tool.md)
- [Resumen de la conversión de ensamblados en bibliotecas de tipos](/previous-versions/dotnet/netframework-4.0/xk1120c3(v=vs.100))
- [TlbImp.exe (Importador de la biblioteca de tipos)](tlbimp-exe-type-library-importer.md)
- [Símbolos del sistema](developer-command-prompt-for-vs.md)
