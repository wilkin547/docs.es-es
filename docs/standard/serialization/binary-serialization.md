---
title: Serialización binaria
ms.date: 01/02/2018
helpviewer_keywords:
- binary serialization
- serialization, about serialization
- deserialization
- binary serialization, about serialization
- binary serialization, .net core serialization
- serialization, cross-framework
ms.assetid: 2b1ea3be-1152-4032-b2b3-07794054c405
author: ViktorHofer
ms.openlocfilehash: 34ba6cb658a52b647c6fbf9a4161d046f31cd73e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705826"
---
# <a name="binary-serialization"></a>Serialización binaria

La serialización se puede definir como el proceso de almacenar el estado de un objeto a los medios de almacenamiento. Durante este proceso, los campos públicos y privados del objeto y el nombre de la clase, incluso el ensamblado que contiene la clase, se convierten en una secuencia de bytes, que se escribe a continuación en un flujo de datos. Cuando se deserializa el objeto como consecuencia, se crea un clon exacto del objeto original.

Al implementar un mecanismo de la serialización en un entorno orientado a objetos, tiene que realizar varios intercambios entre la facilidad de uso y la flexibilidad. El proceso se puede automatizar en gran medida, con tal de que sea proporcionado el control suficiente sobre el proceso. Por ejemplo, las situaciones se pueden presentar donde la serialización binaria simple no es suficiente, o podría haber una razón concreta para decidir qué campos en una clase necesitan ser serializados. Las secciones siguientes examinan el sólido mecanismo de serialización proporcionado con .NET y resaltan varias características importantes que permiten personalizar el proceso para satisfacer las necesidades.

> [!NOTE]
> El estado de un objeto UTF-8 o UTF-7 codificado no se conserva si el objeto se serializa y se deserializa utilizando distintas versiones de .NET Framework.

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

Al igual que la naturaleza de la serialización binaria permite la modificación de los miembros privados de un objeto y, por tanto, cambiar el estado del mismo, se recomiendan otros marcos de trabajo de serialización como JSON.NET que operan en la superficie de la API pública.

## <a name="binary-serialization-in-net-core"></a>Serialización binaria en .NET Core

.NET Core es compatible con la serialización binaria con un subconjunto de tipos. Puede ver la lista de tipos compatibles en la sección [Tipos serializables](#serializable-types). Se garantiza que el conjunto definido de tipos es serializable entre .NET Framework 4.5.1 y versiones posteriores y .NET Core 2.0 y versiones posteriores. Otras implementaciones de .NET, como Mono, no son oficialmente compatibles, pero también deberían funcionar.

### <a name="serializable-types"></a>Tipos serializables

- <xref:Microsoft.CSharp.RuntimeBinder.RuntimeBinderException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:Microsoft.CSharp.RuntimeBinder.RuntimeBinderInternalCompilerException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.AccessViolationException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.AggregateException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.AppDomainUnloadedException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.ApplicationException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.ArgumentException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.ArgumentNullException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.ArgumentOutOfRangeException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.ArithmeticException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Array?displayProperty=nameWithType>
- <xref:System.ArraySegment%601?displayProperty=nameWithType>
- <xref:System.ArrayTypeMismatchException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Attribute?displayProperty=nameWithType>
- <xref:System.BadImageFormatException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Boolean?displayProperty=nameWithType>
- <xref:System.Byte?displayProperty=nameWithType>
- <xref:System.CannotUnloadAppDomainException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Char?displayProperty=nameWithType>
- <xref:System.Collections.ArrayList?displayProperty=nameWithType>
- <xref:System.Collections.BitArray?displayProperty=nameWithType>
- <xref:System.Collections.Comparer?displayProperty=nameWithType>
- <xref:System.Collections.DictionaryEntry?displayProperty=nameWithType>
- <xref:System.Collections.Generic.Comparer%601?displayProperty=nameWithType>
- <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType>
- <xref:System.Collections.Generic.EqualityComparer%601?displayProperty=nameWithType>
- <xref:System.Collections.Generic.HashSet%601?displayProperty=nameWithType>
- <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Collections.Generic.KeyValuePair%602?displayProperty=nameWithType>
- <xref:System.Collections.Generic.LinkedList%601?displayProperty=nameWithType>
- <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>
- <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType>
- <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=nameWithType>
- <xref:System.Collections.Generic.SortedList%602?displayProperty=nameWithType>
- <xref:System.Collections.Generic.SortedSet%601?displayProperty=nameWithType>
- <xref:System.Collections.Generic.Stack%601?displayProperty=nameWithType>
- <xref:System.Collections.Hashtable?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel.Collection%601?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel.KeyedCollection%602?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel.ReadOnlyCollection%601?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel.ReadOnlyDictionary%602?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType>
- <xref:System.Collections.Queue?displayProperty=nameWithType>
- <xref:System.Collections.SortedList?displayProperty=nameWithType>
- <xref:System.Collections.Specialized.HybridDictionary?displayProperty=nameWithType>
- <xref:System.Collections.Specialized.ListDictionary?displayProperty=nameWithType>
- <xref:System.Collections.Specialized.OrderedDictionary?displayProperty=nameWithType>
- <xref:System.Collections.Specialized.StringCollection?displayProperty=nameWithType>
- <xref:System.Collections.Specialized.StringDictionary?displayProperty=nameWithType>
- <xref:System.Collections.Stack?displayProperty=nameWithType>
- `System.Collections.Generic.NonRandomizedStringEqualityComparer` (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.ComponentModel.BindingList%601?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.ValidationException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.ComponentModel.Design.CheckoutException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.ComponentModel.InvalidAsynchronousStateException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.ComponentModel.InvalidEnumArgumentException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.ComponentModel.LicenseException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores, no se admite la serialización de .NET Framework a .NET Core)
- <xref:System.ComponentModel.WarningException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.ComponentModel.Win32Exception?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Configuration.ConfigurationErrorsException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Configuration.ConfigurationException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Configuration.Provider.ProviderException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Configuration.SettingsPropertyIsReadOnlyException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Configuration.SettingsPropertyNotFoundException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Configuration.SettingsPropertyWrongTypeException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.ContextMarshalException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.DBNull?displayProperty=nameWithType> (disponible en .NET Core 2.0.2 y versiones posteriores)
- <xref:System.Data.Common.DbException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Data.ConstraintException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Data.DBConcurrencyException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Data.DataException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Data.DataSet?displayProperty=nameWithType>
- <xref:System.Data.DataTable?displayProperty=nameWithType> (a menos que establezca RemotingFormat en SerializationFormat. Binary, en cuyo caso solo se puede intercambiar con .NET Core 2,1 y versiones posteriores).
- <xref:System.Data.DeletedRowInaccessibleException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Data.DuplicateNameException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Data.EvaluateException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Data.InRowChangingEventException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Data.InvalidConstraintException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Data.InvalidExpressionException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Data.MissingPrimaryKeyException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Data.NoNullAllowedException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Data.Odbc.OdbcException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Data.OperationAbortedException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Data.PropertyCollection?displayProperty=nameWithType>
- <xref:System.Data.ReadOnlyException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Data.RowNotInTableException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Data.SqlClient.SqlException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores, no se admite la serialización de .NET Framework a .NET Core)
- <xref:System.Data.SqlTypes.SqlAlreadyFilledException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Data.SqlTypes.SqlBoolean?displayProperty=nameWithType>
- <xref:System.Data.SqlTypes.SqlByte?displayProperty=nameWithType>
- <xref:System.Data.SqlTypes.SqlDateTime?displayProperty=nameWithType>
- <xref:System.Data.SqlTypes.SqlDouble?displayProperty=nameWithType>
- <xref:System.Data.SqlTypes.SqlGuid?displayProperty=nameWithType>
- <xref:System.Data.SqlTypes.SqlInt16?displayProperty=nameWithType>
- <xref:System.Data.SqlTypes.SqlInt32?displayProperty=nameWithType>
- <xref:System.Data.SqlTypes.SqlInt64?displayProperty=nameWithType>
- <xref:System.Data.SqlTypes.SqlNotFilledException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Data.SqlTypes.SqlNullValueException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Data.SqlTypes.SqlString?displayProperty=nameWithType>
- <xref:System.Data.SqlTypes.SqlTruncateException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Data.SqlTypes.SqlTypeException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Data.StrongTypingException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Data.SyntaxErrorException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Data.VersionNotFoundException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.DataMisalignedException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.DateTime?displayProperty=nameWithType>
- <xref:System.DateTimeOffset?displayProperty=nameWithType>
- <xref:System.Decimal?displayProperty=nameWithType>
- `System.Diagnostics.Contracts.ContractException` (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Diagnostics.Tracing.EventSourceException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.IO.DirectoryNotFoundException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.DirectoryServices.AccountManagement.MultipleMatchesException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.DirectoryServices.AccountManagement.NoMatchingPrincipalException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.DirectoryServices.AccountManagement.PasswordException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.DirectoryServices.AccountManagement.PrincipalException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.DirectoryServices.AccountManagement.PrincipalExistsException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.DirectoryServices.AccountManagement.PrincipalOperationException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.DirectoryServices.AccountManagement.PrincipalServerDownException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryObjectExistsException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryObjectNotFoundException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryOperationException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryServerDownException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.DirectoryServices.ActiveDirectory.ForestTrustCollisionException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.DirectoryServices.ActiveDirectory.SyncFromAllServersOperationException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.DirectoryServices.DirectoryServicesCOMException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.DirectoryServices.Protocols.BerConversionException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.DirectoryServices.Protocols.DirectoryException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.DirectoryServices.Protocols.DirectoryOperationException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.DirectoryServices.Protocols.LdapException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.DirectoryServices.Protocols.TlsOperationException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.DivideByZeroException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.DllNotFoundException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Double?displayProperty=nameWithType>
- <xref:System.Drawing.Color?displayProperty=nameWithType>
- <xref:System.Drawing.Point?displayProperty=nameWithType>
- <xref:System.Drawing.PointF?displayProperty=nameWithType>
- <xref:System.Drawing.Rectangle?displayProperty=nameWithType>
- <xref:System.Drawing.RectangleF?displayProperty=nameWithType>
- <xref:System.Drawing.Size?displayProperty=nameWithType>
- <xref:System.Drawing.SizeF?displayProperty=nameWithType>
- <xref:System.DuplicateWaitObjectException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.EntryPointNotFoundException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Enum?displayProperty=nameWithType>
- <xref:System.EventArgs?displayProperty=nameWithType> (disponible en .NET Core 2.0.6 y versiones posteriores)
- <xref:System.Exception?displayProperty=nameWithType>
- <xref:System.ExecutionEngineException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.FieldAccessException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.FormatException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Globalization.CompareInfo?displayProperty=nameWithType>
- <xref:System.Globalization.CultureNotFoundException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Globalization.SortVersion?displayProperty=nameWithType>
- <xref:System.Guid?displayProperty=nameWithType>
- `System.IO.Compression.ZLibException` (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.IO.DriveNotFoundException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.IO.EndOfStreamException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.IO.FileFormatException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.IO.FileLoadException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.IO.FileNotFoundException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.IO.IOException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.IO.InternalBufferOverflowException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.IO.InvalidDataException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.IO.IsolatedStorage.IsolatedStorageException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.IO.PathTooLongException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.IndexOutOfRangeException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.InsufficientExecutionStackException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.InsufficientMemoryException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Int16?displayProperty=nameWithType>
- <xref:System.Int32?displayProperty=nameWithType>
- <xref:System.Int64?displayProperty=nameWithType>
- <xref:System.IntPtr?displayProperty=nameWithType>
- <xref:System.InvalidCastException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.InvalidOperationException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.InvalidProgramException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.InvalidTimeZoneException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.MemberAccessException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.MethodAccessException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.MissingFieldException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.MissingMemberException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.MissingMethodException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.MulticastNotSupportedException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Net.Cookie?displayProperty=nameWithType>
- <xref:System.Net.CookieCollection?displayProperty=nameWithType>
- <xref:System.Net.CookieContainer?displayProperty=nameWithType>
- <xref:System.Net.CookieException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Net.HttpListenerException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Net.Mail.SmtpException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Net.Mail.SmtpFailedRecipientException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Net.Mail.SmtpFailedRecipientsException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Net.NetworkInformation.NetworkInformationException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Net.NetworkInformation.PingException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Net.ProtocolViolationException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Net.Sockets.SocketException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Net.WebException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Net.WebSockets.WebSocketException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.NotFiniteNumberException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.NotImplementedException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.NotSupportedException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.NullReferenceException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Nullable%601?displayProperty=nameWithType>
- <xref:System.Numerics.BigInteger?displayProperty=nameWithType>
- <xref:System.Numerics.Complex?displayProperty=nameWithType>
- <xref:System.Object?displayProperty=nameWithType>
- <xref:System.ObjectDisposedException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.OperationCanceledException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.OutOfMemoryException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.OverflowException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.PlatformNotSupportedException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.RankException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Reflection.AmbiguousMatchException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Reflection.CustomAttributeFormatException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Reflection.InvalidFilterCriteriaException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Reflection.ReflectionTypeLoadException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores, no se admite la serialización de .NET Framework a .NET Core)
- <xref:System.Reflection.TargetException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Reflection.TargetInvocationException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Reflection.TargetParameterCountException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Resources.MissingManifestResourceException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Resources.MissingSatelliteAssemblyException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Runtime.CompilerServices.RuntimeWrappedException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Runtime.InteropServices.COMException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Runtime.InteropServices.ExternalException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Runtime.InteropServices.InvalidComObjectException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Runtime.InteropServices.InvalidOleVariantTypeException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Runtime.InteropServices.MarshalDirectiveException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Runtime.InteropServices.SEHException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Runtime.Serialization.InvalidDataContractException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Runtime.Serialization.SerializationException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.SByte?displayProperty=nameWithType>
- <xref:System.Security.AccessControl.PrivilegeNotHeldException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Security.Authentication.AuthenticationException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Security.Authentication.InvalidCredentialException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Security.Cryptography.CryptographicException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Security.Cryptography.CryptographicUnexpectedOperationException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- `System.Security.Cryptography.Xml.CryptoSignedXmlRecursionException` (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Security.HostProtectionException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Security.Policy.PolicyException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Security.Principal.IdentityNotMappedException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Security.SecurityException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores, datos de serialización limitados)
- <xref:System.Security.VerificationException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Security.XmlSyntaxException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.ServiceProcess.TimeoutException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Single?displayProperty=nameWithType>
- <xref:System.StackOverflowException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.String?displayProperty=nameWithType>
- <xref:System.StringComparer?displayProperty=nameWithType>
- <xref:System.SystemException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Text.DecoderFallbackException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Text.EncoderFallbackException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Text.RegularExpressions.RegexMatchTimeoutException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Text.StringBuilder?displayProperty=nameWithType>
- <xref:System.Threading.AbandonedMutexException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Threading.BarrierPostPhaseException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Threading.LockRecursionException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Threading.SemaphoreFullException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Threading.SynchronizationLockException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Threading.Tasks.TaskCanceledException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Threading.Tasks.TaskSchedulerException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Threading.ThreadAbortException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Threading.ThreadInterruptedException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Threading.ThreadStartException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Threading.ThreadStateException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Threading.WaitHandleCannotBeOpenedException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.TimeSpan?displayProperty=nameWithType>
- <xref:System.TimeZoneInfo.AdjustmentRule?displayProperty=nameWithType>
- <xref:System.TimeZoneInfo?displayProperty=nameWithType>
- <xref:System.TimeZoneNotFoundException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.TimeoutException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Transactions.TransactionAbortedException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Transactions.TransactionException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Transactions.TransactionInDoubtException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Transactions.TransactionManagerCommunicationException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Transactions.TransactionPromotionException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Tuple?displayProperty=nameWithType>
- <xref:System.TypeAccessException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.TypeInitializationException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.TypeLoadException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.TypeUnloadedException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.UInt16?displayProperty=nameWithType>
- <xref:System.UInt32?displayProperty=nameWithType>
- <xref:System.UInt64?displayProperty=nameWithType>
- <xref:System.UIntPtr?displayProperty=nameWithType>
- <xref:System.UnauthorizedAccessException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Uri?displayProperty=nameWithType>
- <xref:System.UriFormatException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.ValueTuple?displayProperty=nameWithType> (no serializable en .NET Framework 4,7 y versiones anteriores)
- <xref:System.ValueType?displayProperty=nameWithType>
- <xref:System.Version?displayProperty=nameWithType>
- <xref:System.WeakReference%601?displayProperty=nameWithType>
- <xref:System.WeakReference?displayProperty=nameWithType>
- <xref:System.Xml.Schema.XmlSchemaException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Xml.Schema.XmlSchemaInferenceException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Xml.Schema.XmlSchemaValidationException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Xml.XPath.XPathException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Xml.XmlException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Xml.Xsl.XsltCompileException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)
- <xref:System.Xml.Xsl.XsltException?displayProperty=nameWithType> (disponible en .NET Core 2.0.4 y versiones posteriores)

## <a name="in-this-section"></a>En esta sección

- [Conceptos de serialización](../../../docs/standard/serialization/serialization-concepts.md)\
Describe dos escenarios en los que la serialización resulta útil: al almacenar datos persistentes y al pasar objetos a través de dominios de aplicaciones.

- [Serialización básica](../../../docs/standard/serialization/basic-serialization.md)\
Describe cómo utilizar los formateadores SOAP y binario para serializar los objetos.

- \ de [Serialización selectiva](../../../docs/standard/serialization/selective-serialization.md)
Describe cómo evitar que se serialicen algunos miembros de una clase.

- \ de [serialización personalizada](../../../docs/standard/serialization/custom-serialization.md)
Describe cómo personalizar la serialización de una clase mediante la interfaz <xref:System.Runtime.Serialization.ISerializable>.

- [Pasos del proceso de serialización](../../../docs/standard/serialization/steps-in-the-serialization-process.md)\
Describe la medida que toma la serialización cuando se llama al método <xref:System.Runtime.Serialization.Formatter.Serialize%2A> en un formateador.

- \ de [serialización tolerante a versiones](../../../docs/standard/serialization/version-tolerant-serialization.md)
Explica cómo crear tipos serializables que se pueden modificar con el tiempo sin hacer que las aplicaciones produzcan las excepciones.

- [Instrucciones de serialización](../../../docs/standard/serialization/serialization-guidelines.md)\
Proporciona algunas directrices general para decidir cuándo serializar un objeto.

## <a name="reference"></a>Referencia

- <xref:System.Runtime.Serialization>\
Contiene clases que se pueden usar para serializar y deserializar objetos.

## <a name="related-sections"></a>Secciones relacionadas

- [Serialización SOAP y XML](../../../docs/standard/serialization/xml-and-soap-serialization.md)\
Describe el mecanismo de la serialización XML que está incluido con Common Language Runtime.

- \ [de seguridad y serialización](../../../docs/framework/misc/security-and-serialization.md)
Describe las instrucciones de la codificación seguras que hay que seguir al escribir el código que realiza la serialización.

- \ [.NET Remoting](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100))
Describe los diversos métodos de comunicaciones disponibles en .NET Framework para las comunicaciones remotas.

- [Servicios Web XML creados mediante ASP.net y clientes de servicios web xml](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))\
Proporciona los temas que describen y explican cómo programar los servicios Web XML creados utilizando ASP.NET.
