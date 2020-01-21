---
title: API no admitidas en .NET Core
description: Obtenga información sobre qué API de .NET Framework siempre producen una excepción en .NET Core.
ms.date: 12/23/2019
ms.openlocfilehash: f27aeca31226a95dacf100813762eedb56876fbd
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2020
ms.locfileid: "75936974"
---
# <a name="apis-that-always-throw-exceptions-on-net-core"></a><span data-ttu-id="85613-103">API que siempre producen excepciones en .NET Core</span><span class="sxs-lookup"><span data-stu-id="85613-103">APIs that always throw exceptions on .NET Core</span></span>

<span data-ttu-id="85613-104">Las siguientes API siempre producirán una <xref:System.PlatformNotSupportedException> en .NET Core en todas las plataformas, o bien en un subconjunto de estas.</span><span class="sxs-lookup"><span data-stu-id="85613-104">The following APIs will always throw a <xref:System.PlatformNotSupportedException> on .NET Core on all or a subset of platforms.</span></span>

<span data-ttu-id="85613-105">En este artículo se organizan los miembros de API afectados por el espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="85613-105">This article organizes the affected API members by namespace.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="85613-106">Este artículo sigue en desarrollo.</span><span class="sxs-lookup"><span data-stu-id="85613-106">This article is a work-in-progress.</span></span> <span data-ttu-id="85613-107">No es una lista completa de las API que producen excepciones en .NET Core.</span><span class="sxs-lookup"><span data-stu-id="85613-107">It is not a complete list of APIs that throw exceptions on .NET Core.</span></span>
> - <span data-ttu-id="85613-108">En este artículo no se incluyen las implementaciones de interfaz explícitas para la serialización binaria que se inician en .NET Core.</span><span class="sxs-lookup"><span data-stu-id="85613-108">This article does not include the explicit interface implementations for binary serialization that throw on .NET Core.</span></span> <span data-ttu-id="85613-109">Para obtener más información, vea [Serialización binaria en .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span><span class="sxs-lookup"><span data-stu-id="85613-109">For more information, see [Binary serialization in .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span></span>

## <a name="system"></a><span data-ttu-id="85613-110">Sistema</span><span class="sxs-lookup"><span data-stu-id="85613-110">System</span></span>

| <span data-ttu-id="85613-111">Miembro</span><span class="sxs-lookup"><span data-stu-id="85613-111">Member</span></span> | <span data-ttu-id="85613-112">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="85613-112">Platforms that throw</span></span> |
| - | - |
| <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> | <span data-ttu-id="85613-113">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-113">All</span></span> |
| <xref:System.AppDomain.ExecuteAssembly(System.String,System.String[],System.Byte[],System.Configuration.Assemblies.AssemblyHashAlgorithm)?displayProperty=nameWithType> | <span data-ttu-id="85613-114">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-114">All</span></span> |
| <xref:System.Console.CapsLock?displayProperty=nameWithType> | <span data-ttu-id="85613-115">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="85613-115">Linux and macOS</span></span> |
| <xref:System.Console.NumberLock?displayProperty=nameWithType> | <span data-ttu-id="85613-116">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="85613-116">Linux and macOS</span></span> |
| <xref:System.Delegate.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="85613-117">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-117">All</span></span> |
| <xref:System.Exception.SerializeObjectState?displayProperty=nameWithType> | <span data-ttu-id="85613-118">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-118">All</span></span> |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="85613-119">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-119">All</span></span> |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="85613-120">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-120">All</span></span> |
| <xref:System.OperatingSystem.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="85613-121">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-121">All</span></span> |
| <xref:System.Type.ReflectionOnlyGetType(System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="85613-122">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-122">All</span></span> |

## <a name="systemcodedomcompiler"></a><span data-ttu-id="85613-123">System.CodeDom.Compiler</span><span class="sxs-lookup"><span data-stu-id="85613-123">System.CodeDom.Compiler</span></span>

| <span data-ttu-id="85613-124">Miembro</span><span class="sxs-lookup"><span data-stu-id="85613-124">Member</span></span> | <span data-ttu-id="85613-125">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="85613-125">Platforms that throw</span></span> |
| - | - |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A?displayProperty=nameWithType> | <span data-ttu-id="85613-126">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-126">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A?displayProperty=nameWithType> | <span data-ttu-id="85613-127">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-127">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A?displayProperty=nameWithType> | <span data-ttu-id="85613-128">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-128">All</span></span> |

## <a name="systemcollectionsspecialized"></a><span data-ttu-id="85613-129">System.Collections.Specialized</span><span class="sxs-lookup"><span data-stu-id="85613-129">System.Collections.Specialized</span></span>

| <span data-ttu-id="85613-130">Miembro</span><span class="sxs-lookup"><span data-stu-id="85613-130">Member</span></span> | <span data-ttu-id="85613-131">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="85613-131">Platforms that throw</span></span> |
| - | - |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="85613-132">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-132">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="85613-133">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-133">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="85613-134">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-134">All</span></span> |

## <a name="systemconfiguration"></a><span data-ttu-id="85613-135">System.Configuration</span><span class="sxs-lookup"><span data-stu-id="85613-135">System.Configuration</span></span>

| <span data-ttu-id="85613-136">Miembro</span><span class="sxs-lookup"><span data-stu-id="85613-136">Member</span></span> | <span data-ttu-id="85613-137">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="85613-137">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="85613-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (todos los miembros)</span><span class="sxs-lookup"><span data-stu-id="85613-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (all members)</span></span> | <span data-ttu-id="85613-139">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-139">All</span></span> |

## <a name="systemconsole"></a><span data-ttu-id="85613-140">System.Console</span><span class="sxs-lookup"><span data-stu-id="85613-140">System.Console</span></span>

| <span data-ttu-id="85613-141">Miembro</span><span class="sxs-lookup"><span data-stu-id="85613-141">Member</span></span> | <span data-ttu-id="85613-142">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="85613-142">Platforms that throw</span></span> |
| - | - |
| <xref:System.Console.Beep?displayProperty=nameWithType> | <span data-ttu-id="85613-143">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="85613-143">Linux and macOS</span></span> |
| <span data-ttu-id="85613-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="85613-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="85613-145">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="85613-145">Linux and macOS</span></span> |
| <span data-ttu-id="85613-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="85613-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="85613-147">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="85613-147">Linux and macOS</span></span> |
| <span data-ttu-id="85613-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="85613-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="85613-149">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="85613-149">Linux and macOS</span></span> |
| <span data-ttu-id="85613-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (solo Obtener)</span><span class="sxs-lookup"><span data-stu-id="85613-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="85613-151">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="85613-151">Linux and macOS</span></span> |
| <xref:System.Console.MoveBufferArea%2A?displayProperty=nameWithType> | <span data-ttu-id="85613-152">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="85613-152">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowPosition%2A?displayProperty=nameWithType> | <span data-ttu-id="85613-153">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="85613-153">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowSize%2A?displayProperty=nameWithType> | <span data-ttu-id="85613-154">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="85613-154">Linux and macOS</span></span> |
| <span data-ttu-id="85613-155"><xref:System.Console.Title?displayProperty=nameWithType> (solo Obtener)</span><span class="sxs-lookup"><span data-stu-id="85613-155"><xref:System.Console.Title?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="85613-156">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="85613-156">Linux and macOS</span></span> |
| <span data-ttu-id="85613-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="85613-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="85613-158">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="85613-158">Linux and macOS</span></span> |
| <span data-ttu-id="85613-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="85613-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="85613-160">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="85613-160">Linux and macOS</span></span> |
| <span data-ttu-id="85613-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="85613-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="85613-162">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="85613-162">Linux and macOS</span></span> |
| <span data-ttu-id="85613-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="85613-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="85613-164">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="85613-164">Linux and macOS</span></span> |

## <a name="systemdatacommon"></a><span data-ttu-id="85613-165">System.Data.Common</span><span class="sxs-lookup"><span data-stu-id="85613-165">System.Data.Common</span></span>

| <span data-ttu-id="85613-166">Miembro</span><span class="sxs-lookup"><span data-stu-id="85613-166">Member</span></span> | <span data-ttu-id="85613-167">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="85613-167">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="85613-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (genera <xref:System.NotSupportedException>)</span><span class="sxs-lookup"><span data-stu-id="85613-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (throws <xref:System.NotSupportedException>)</span></span> | <span data-ttu-id="85613-169">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-169">All</span></span> |

## <a name="systemdiagnosticsprocess"></a><span data-ttu-id="85613-170">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="85613-170">System.Diagnostics.Process</span></span>

| <span data-ttu-id="85613-171">Miembro</span><span class="sxs-lookup"><span data-stu-id="85613-171">Member</span></span> | <span data-ttu-id="85613-172">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="85613-172">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="85613-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="85613-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="85613-174">Linux</span><span class="sxs-lookup"><span data-stu-id="85613-174">Linux</span></span> |
| <span data-ttu-id="85613-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="85613-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="85613-176">Linux</span><span class="sxs-lookup"><span data-stu-id="85613-176">Linux</span></span> |
| <xref:System.Diagnostics.Process.ProcessorAffinity?displayProperty=nameWithType> | <span data-ttu-id="85613-177">macOS</span><span class="sxs-lookup"><span data-stu-id="85613-177">macOS</span></span> |
| <xref:System.Diagnostics.Process.MainWindowHandle?displayProperty=nameWithType> | <span data-ttu-id="85613-178">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="85613-178">Linux and macOS</span></span> |
| <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> | <span data-ttu-id="85613-179">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="85613-179">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.UserName?displayProperty=nameWithType> | <span data-ttu-id="85613-180">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="85613-180">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.PasswordInClearText?displayProperty=nameWithType> | <span data-ttu-id="85613-181">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="85613-181">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.Domain?displayProperty=nameWithType> | <span data-ttu-id="85613-182">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="85613-182">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.LoadUserProfile?displayProperty=nameWithType> | <span data-ttu-id="85613-183">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="85613-183">Linux and macOS</span></span> |
| <span data-ttu-id="85613-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="85613-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="85613-185">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="85613-185">Linux and macOS</span></span> |
| <span data-ttu-id="85613-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (solo Obtener)</span><span class="sxs-lookup"><span data-stu-id="85613-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="85613-187">macOS</span><span class="sxs-lookup"><span data-stu-id="85613-187">macOS</span></span> |
| <span data-ttu-id="85613-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="85613-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="85613-189">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="85613-189">Linux and macOS</span></span> |

## <a name="systemio"></a><span data-ttu-id="85613-190">System.IO</span><span class="sxs-lookup"><span data-stu-id="85613-190">System.IO</span></span>

| <span data-ttu-id="85613-191">Miembro</span><span class="sxs-lookup"><span data-stu-id="85613-191">Member</span></span> | <span data-ttu-id="85613-192">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="85613-192">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.FileSystemInfo.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="85613-193">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-193">All</span></span> |
| <xref:System.IO.FileSystemInfo.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="85613-194">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-194">All</span></span> |

## <a name="systemiopipes"></a><span data-ttu-id="85613-195">System.IO.Pipes</span><span class="sxs-lookup"><span data-stu-id="85613-195">System.IO.Pipes</span></span>

| <span data-ttu-id="85613-196">Miembro</span><span class="sxs-lookup"><span data-stu-id="85613-196">Member</span></span> | <span data-ttu-id="85613-197">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="85613-197">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.Pipes.NamedPipeClientStream.NumberOfServerInstances?displayProperty=nameWithType> | <span data-ttu-id="85613-198">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="85613-198">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName?displayProperty=nameWithType> | <span data-ttu-id="85613-199">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="85613-199">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.InBufferSize?displayProperty=nameWithType> | <span data-ttu-id="85613-200">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="85613-200">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.OutBufferSize?displayProperty=nameWithType> | <span data-ttu-id="85613-201">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="85613-201">Linux and macOS</span></span> |
| <span data-ttu-id="85613-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="85613-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="85613-203">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="85613-203">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.WaitForPipeDrain?displayProperty=nameWithType> | <span data-ttu-id="85613-204">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="85613-204">Linux and macOS</span></span> |

## <a name="systemmedia"></a><span data-ttu-id="85613-205">System.Media</span><span class="sxs-lookup"><span data-stu-id="85613-205">System.Media</span></span>

| <span data-ttu-id="85613-206">Miembro</span><span class="sxs-lookup"><span data-stu-id="85613-206">Member</span></span> | <span data-ttu-id="85613-207">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="85613-207">Platforms that throw</span></span> |
| - | - |
| <xref:System.Media.SoundPlayer.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="85613-208">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-208">All</span></span> |

## <a name="systemnet"></a><span data-ttu-id="85613-209">System.Net</span><span class="sxs-lookup"><span data-stu-id="85613-209">System.Net</span></span>

| <span data-ttu-id="85613-210">Miembro</span><span class="sxs-lookup"><span data-stu-id="85613-210">Member</span></span> | <span data-ttu-id="85613-211">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="85613-211">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.AuthenticationManager.Authenticate(System.String,System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="85613-212">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-212">All</span></span> |
| <xref:System.Net.AuthenticationManager.PreAuthenticate(System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="85613-213">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-213">All</span></span> |
| <xref:System.Net.FileWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="85613-214">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-214">All</span></span> |
| <xref:System.Net.FileWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="85613-215">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-215">All</span></span> |
| <xref:System.Net.FileWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="85613-216">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-216">All</span></span> |
| <xref:System.Net.FileWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="85613-217">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-217">All</span></span> |
| <xref:System.Net.HttpWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="85613-218">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-218">All</span></span> |
| <xref:System.Net.HttpWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="85613-219">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-219">All</span></span> |
| <xref:System.Net.HttpWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="85613-220">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-220">All</span></span> |
| <xref:System.Net.HttpWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="85613-221">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-221">All</span></span> |
| <xref:System.Net.WebProxy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="85613-222">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-222">All</span></span> |
| <xref:System.Net.WebProxy.GetDefaultProxy?displayProperty=nameWithType> | <span data-ttu-id="85613-223">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-223">All</span></span> |
| <xref:System.Net.WebProxy.GetObjectData%2A?displayProperty=nameWithType> | <span data-ttu-id="85613-224">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-224">All</span></span> |
| <xref:System.Net.WebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="85613-225">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-225">All</span></span> |
| <xref:System.Net.WebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="85613-226">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-226">All</span></span> |
| <xref:System.Net.WebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="85613-227">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-227">All</span></span> |
| <xref:System.Net.WebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="85613-228">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-228">All</span></span> |

## <a name="systemnetnetworkinformation"></a><span data-ttu-id="85613-229">System.Net.NetworkInformation</span><span class="sxs-lookup"><span data-stu-id="85613-229">System.Net.NetworkInformation</span></span>

| <span data-ttu-id="85613-230">Miembro</span><span class="sxs-lookup"><span data-stu-id="85613-230">Member</span></span> | <span data-ttu-id="85613-231">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="85613-231">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.NetworkInformation.Ping.Send%2A?displayProperty=nameWithType> | <span data-ttu-id="85613-232">Windows (UWP)</span><span class="sxs-lookup"><span data-stu-id="85613-232">Windows (UWP)</span></span> |

## <a name="systemnetsockets"></a><span data-ttu-id="85613-233">System.Net.Sockets</span><span class="sxs-lookup"><span data-stu-id="85613-233">System.Net.Sockets</span></span>

| <span data-ttu-id="85613-234">Miembro</span><span class="sxs-lookup"><span data-stu-id="85613-234">Member</span></span> | <span data-ttu-id="85613-235">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="85613-235">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.Sockets.Socket.DuplicateAndClose(System.Int32)?displayProperty=nameWithType> | <span data-ttu-id="85613-236">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-236">All</span></span> |

## <a name="systemnetwebsockets"></a><span data-ttu-id="85613-237">System.Net.WebSockets</span><span class="sxs-lookup"><span data-stu-id="85613-237">System.Net.WebSockets</span></span>

| <span data-ttu-id="85613-238">Miembro</span><span class="sxs-lookup"><span data-stu-id="85613-238">Member</span></span> | <span data-ttu-id="85613-239">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="85613-239">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.WebSockets.WebSocket.RegisterPrefixes?displayProperty=nameWithType> | <span data-ttu-id="85613-240">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-240">All</span></span> |

## <a name="systemreflection"></a><span data-ttu-id="85613-241">System.Reflection</span><span class="sxs-lookup"><span data-stu-id="85613-241">System.Reflection</span></span>

| <span data-ttu-id="85613-242">Miembro</span><span class="sxs-lookup"><span data-stu-id="85613-242">Member</span></span> | <span data-ttu-id="85613-243">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="85613-243">Platforms that throw</span></span> |
| - | - |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> | <span data-ttu-id="85613-244">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-244">All</span></span> |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom(System.String)?displayProperty=nameWithType> | <span data-ttu-id="85613-245">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-245">All</span></span> |
| <xref:System.Reflection.AssemblyName.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="85613-246">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-246">All</span></span> |
| <xref:System.Reflection.AssemblyName.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="85613-247">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-247">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.String)?displayProperty=nameWithType> | <span data-ttu-id="85613-248">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-248">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="85613-249">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-249">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.PublicKey?displayProperty=nameWithType> | <span data-ttu-id="85613-250">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-250">All</span></span> |

## <a name="systemruntimecompilerservices"></a><span data-ttu-id="85613-251">System.Runtime.CompilerServices</span><span class="sxs-lookup"><span data-stu-id="85613-251">System.Runtime.CompilerServices</span></span>

| <span data-ttu-id="85613-252">Miembro</span><span class="sxs-lookup"><span data-stu-id="85613-252">Member</span></span> | <span data-ttu-id="85613-253">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="85613-253">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> | <span data-ttu-id="85613-254">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-254">All</span></span> |

## <a name="systemruntimeinteropservices"></a><span data-ttu-id="85613-255">System.Runtime.InteropServices</span><span class="sxs-lookup"><span data-stu-id="85613-255">System.Runtime.InteropServices</span></span>

| <span data-ttu-id="85613-256">Miembro</span><span class="sxs-lookup"><span data-stu-id="85613-256">Member</span></span> | <span data-ttu-id="85613-257">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="85613-257">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.InteropServices.Marshal.GetIDispatchForObject(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="85613-258">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-258">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.SystemConfigurationFile?displayProperty=nameWithType> | <span data-ttu-id="85613-259">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-259">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsIntPtr(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="85613-260">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-260">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsObject(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="85613-261">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-261">All</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.StringToHString(System.String)?displayProperty=nameWithType> | <span data-ttu-id="85613-262">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="85613-262">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.PtrToStringHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="85613-263">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="85613-263">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.FreeHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="85613-264">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="85613-264">Linux and macOS</span></span> |

## <a name="systemruntimeserialization"></a><span data-ttu-id="85613-265">System.Runtime.Serialization</span><span class="sxs-lookup"><span data-stu-id="85613-265">System.Runtime.Serialization</span></span>

| <span data-ttu-id="85613-266">Miembro</span><span class="sxs-lookup"><span data-stu-id="85613-266">Member</span></span> | <span data-ttu-id="85613-267">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="85613-267">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.Serialization.XsdDataContractExporter.Schemas?displayProperty=nameWithType> | <span data-ttu-id="85613-268">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-268">All</span></span> |

## <a name="systemsecurity"></a><span data-ttu-id="85613-269">System.Security</span><span class="sxs-lookup"><span data-stu-id="85613-269">System.Security</span></span>

| <span data-ttu-id="85613-270">Miembro</span><span class="sxs-lookup"><span data-stu-id="85613-270">Member</span></span> | <span data-ttu-id="85613-271">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="85613-271">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.CodeAccessPermission.Deny?displayProperty=nameWithType> | <span data-ttu-id="85613-272">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-272">All</span></span> |
| <xref:System.Security.CodeAccessPermission.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="85613-273">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-273">All</span></span> |
| <xref:System.Security.PermissionSet.ConvertPermissionSet(System.String,System.Byte[],System.String)?displayProperty=nameWithType> | <span data-ttu-id="85613-274">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-274">All</span></span> |
| <xref:System.Security.PermissionSet.Deny?displayProperty=nameWithType> | <span data-ttu-id="85613-275">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-275">All</span></span> |
| <xref:System.Security.PermissionSet.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="85613-276">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-276">All</span></span> |
| <xref:System.Security.SecurityContext.Capture?displayProperty=nameWithType> | <span data-ttu-id="85613-277">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-277">All</span></span> |
| <xref:System.Security.SecurityContext.CreateCopy?displayProperty=nameWithType> | <span data-ttu-id="85613-278">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-278">All</span></span> |
| <xref:System.Security.SecurityContext.Dispose?displayProperty=nameWithType> | <span data-ttu-id="85613-279">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-279">All</span></span> |
| <xref:System.Security.SecurityContext.IsFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="85613-280">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-280">All</span></span> |
| <xref:System.Security.SecurityContext.IsWindowsIdentityFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="85613-281">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-281">All</span></span> |
| <xref:System.Security.SecurityContext.RestoreFlow?displayProperty=nameWithType> | <span data-ttu-id="85613-282">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-282">All</span></span> |
| <xref:System.Security.SecurityContext.Run(System.Security.SecurityContext,System.Threading.ContextCallback,System.Object)?displayProperty=nameWithType> | <span data-ttu-id="85613-283">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-283">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlow?displayProperty=nameWithType> | <span data-ttu-id="85613-284">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-284">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity?displayProperty=nameWithType> | <span data-ttu-id="85613-285">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-285">All</span></span> |

## <a name="systemsecurityclaims"></a><span data-ttu-id="85613-286">System.Security.Claims</span><span class="sxs-lookup"><span data-stu-id="85613-286">System.Security.Claims</span></span>

| <span data-ttu-id="85613-287">Miembro</span><span class="sxs-lookup"><span data-stu-id="85613-287">Member</span></span> | <span data-ttu-id="85613-288">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="85613-288">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Claims.ClaimsPrincipal.%23ctor?displayProperty=nameWithType> | <span data-ttu-id="85613-289">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-289">All</span></span> |
| <xref:System.Security.Claims.ClaimsPrincipal.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="85613-290">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-290">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo)?displayProperty=nameWithType> | <span data-ttu-id="85613-291">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-291">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="85613-292">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-292">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="85613-293">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-293">All</span></span> |

## <a name="systemsecuritycryptography"></a><span data-ttu-id="85613-294">System.Security.Cryptography</span><span class="sxs-lookup"><span data-stu-id="85613-294">System.Security.Cryptography</span></span>

| <span data-ttu-id="85613-295">Miembro</span><span class="sxs-lookup"><span data-stu-id="85613-295">Member</span></span> | <span data-ttu-id="85613-296">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="85613-296">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="85613-297">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-297">All</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.%23ctor%2A?displayProperty=nameWithType> | <span data-ttu-id="85613-298">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="85613-298">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Accessible?displayProperty=nameWithType> | <span data-ttu-id="85613-299">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="85613-299">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Exportable?displayProperty=nameWithType> | <span data-ttu-id="85613-300">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="85613-300">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.HardwareDevice?displayProperty=nameWithType> | <span data-ttu-id="85613-301">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="85613-301">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="85613-302">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="85613-302">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyNumber?displayProperty=nameWithType> | <span data-ttu-id="85613-303">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="85613-303">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.MachineKeyStore?displayProperty=nameWithType> | <span data-ttu-id="85613-304">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="85613-304">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Protected?displayProperty=nameWithType> | <span data-ttu-id="85613-305">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="85613-305">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderName?displayProperty=nameWithType> | <span data-ttu-id="85613-306">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="85613-306">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderType?displayProperty=nameWithType> | <span data-ttu-id="85613-307">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="85613-307">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.RandomlyGenerated?displayProperty=nameWithType> | <span data-ttu-id="85613-308">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="85613-308">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Removable?displayProperty=nameWithType> | <span data-ttu-id="85613-309">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="85613-309">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.UniqueKeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="85613-310">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="85613-310">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="85613-311">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-311">All</span></span> |
| <xref:System.Security.Cryptography.HashAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="85613-312">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-312">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | <span data-ttu-id="85613-313">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-313">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="85613-314">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-314">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashCore%2A?displayProperty=nameWithType> | <span data-ttu-id="85613-315">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-315">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashFinal%2A?displayProperty=nameWithType> | <span data-ttu-id="85613-316">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-316">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Initialize%2A?displayProperty=nameWithType> | <span data-ttu-id="85613-317">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-317">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="85613-318">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-318">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="85613-319">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-319">All</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Protect%2A?displayProperty=nameWithType> | <span data-ttu-id="85613-320">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="85613-320">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A?displayProperty=nameWithType> | <span data-ttu-id="85613-321">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="85613-321">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.RSA.FromXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="85613-322">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-322">All</span></span> |
| <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="85613-323">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-323">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="85613-324">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-324">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="85613-325">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-325">All</span></span> |

## <a name="systemsecuritycryptographypkcs"></a><span data-ttu-id="85613-326">System.Security.Cryptography.Pkcs</span><span class="sxs-lookup"><span data-stu-id="85613-326">System.Security.Cryptography.Pkcs</span></span>

| <span data-ttu-id="85613-327">Miembro</span><span class="sxs-lookup"><span data-stu-id="85613-327">Member</span></span> | <span data-ttu-id="85613-328">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="85613-328">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.Pkcs.CmsSigner.%23ctor(System.Security.Cryptography.CspParameters)?displayProperty=nameWithType> | <span data-ttu-id="85613-329">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-329">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="85613-330">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-330">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignerInfo.ComputeCounterSignature?displayProperty=nameWithType> | <span data-ttu-id="85613-331">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-331">All</span></span> |

## <a name="systemsecuritycryptographyx509certificates"></a><span data-ttu-id="85613-332">System.Security.Cryptography.X509Certificates</span><span class="sxs-lookup"><span data-stu-id="85613-332">System.Security.Cryptography.X509Certificates</span></span>

| <span data-ttu-id="85613-333">Miembro</span><span class="sxs-lookup"><span data-stu-id="85613-333">Member</span></span> | <span data-ttu-id="85613-334">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="85613-334">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="85613-335">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-335">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Import%2A?displayProperty=nameWithType> | <span data-ttu-id="85613-336">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-336">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="85613-337">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-337">All</span></span> |
| <span data-ttu-id="85613-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="85613-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="85613-339">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-339">All</span></span> |

## <a name="systemsecurityauthenticationextendedprotection"></a><span data-ttu-id="85613-340">System.Security.Authentication.ExtendedProtection</span><span class="sxs-lookup"><span data-stu-id="85613-340">System.Security.Authentication.ExtendedProtection</span></span>

| <span data-ttu-id="85613-341">Miembro</span><span class="sxs-lookup"><span data-stu-id="85613-341">Member</span></span> | <span data-ttu-id="85613-342">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="85613-342">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="85613-343">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-343">All</span></span> |

## <a name="systemsecuritypolicy"></a><span data-ttu-id="85613-344">System.Security.Policy</span><span class="sxs-lookup"><span data-stu-id="85613-344">System.Security.Policy</span></span>

| <span data-ttu-id="85613-345">Miembro</span><span class="sxs-lookup"><span data-stu-id="85613-345">Member</span></span> | <span data-ttu-id="85613-346">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="85613-346">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Policy.Hash.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="85613-347">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-347">All</span></span> |

## <a name="systemserviceprocessservicecontroller"></a><span data-ttu-id="85613-348">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="85613-348">System.ServiceProcess.ServiceController</span></span>

| <span data-ttu-id="85613-349">Miembro</span><span class="sxs-lookup"><span data-stu-id="85613-349">Member</span></span> | <span data-ttu-id="85613-350">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="85613-350">Platforms that throw</span></span> |
| - | - |
| <xref:System.ServiceProcess.TimeoutException.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="85613-351">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-351">All</span></span> |

## <a name="systemtextregularexpressions"></a><span data-ttu-id="85613-352">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="85613-352">System.Text.RegularExpressions</span></span>

| <span data-ttu-id="85613-353">Miembro</span><span class="sxs-lookup"><span data-stu-id="85613-353">Member</span></span> | <span data-ttu-id="85613-354">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="85613-354">Platforms that throw</span></span> |
| - | - |
| <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType> | <span data-ttu-id="85613-355">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-355">All</span></span> |

## <a name="systemthreading"></a><span data-ttu-id="85613-356">System.Threading</span><span class="sxs-lookup"><span data-stu-id="85613-356">System.Threading</span></span>

| <span data-ttu-id="85613-357">Miembro</span><span class="sxs-lookup"><span data-stu-id="85613-357">Member</span></span> | <span data-ttu-id="85613-358">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="85613-358">Platforms that throw</span></span> |
| - | - |
| <xref:System.Threading.CompressedStack.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="85613-359">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-359">All</span></span> |
| <xref:System.Threading.ExecutionContext.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="85613-360">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-360">All</span></span> |
| <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> | <span data-ttu-id="85613-361">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-361">All</span></span> |
| <xref:System.Threading.Thread.ResetAbort?displayProperty=nameWithType> | <span data-ttu-id="85613-362">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-362">All</span></span> |
| <xref:System.Threading.Thread.Resume?displayProperty=nameWithType> | <span data-ttu-id="85613-363">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-363">All</span></span> |
| <xref:System.Threading.Thread.Suspend?displayProperty=nameWithType> | <span data-ttu-id="85613-364">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-364">All</span></span> |

## <a name="systemxml"></a><span data-ttu-id="85613-365">System.Xml</span><span class="sxs-lookup"><span data-stu-id="85613-365">System.Xml</span></span>

| <span data-ttu-id="85613-366">Miembro</span><span class="sxs-lookup"><span data-stu-id="85613-366">Member</span></span> | <span data-ttu-id="85613-367">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="85613-367">Platforms that throw</span></span> |
| - | - |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.Byte[],System.Int32,System.Int32,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="85613-368">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-368">All</span></span> |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.IO.Stream,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="85613-369">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-369">All</span></span> |
| <xref:System.Xml.XmlDictionaryWriter.CreateMtomWriter(System.IO.Stream,System.Text.Encoding,System.Int32,System.String,System.String,System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="85613-370">Todas</span><span class="sxs-lookup"><span data-stu-id="85613-370">All</span></span> |

## <a name="see-also"></a><span data-ttu-id="85613-371">Vea también</span><span class="sxs-lookup"><span data-stu-id="85613-371">See also</span></span>

- [<span data-ttu-id="85613-372">Cambios importantes para la migración desde .NET Framework a .NET Core</span><span class="sxs-lookup"><span data-stu-id="85613-372">Breaking changes for migration from .NET Framework to .NET Core</span></span>](../compatibility/fx-core.md)
- [<span data-ttu-id="85613-373">Serialización binaria en .NET Core</span><span class="sxs-lookup"><span data-stu-id="85613-373">Binary serialization in .NET Core</span></span>](../../standard/serialization/binary-serialization.md#net-core)
- [<span data-ttu-id="85613-374">Analizador de portabilidad de .NET</span><span class="sxs-lookup"><span data-stu-id="85613-374">.NET portability analyzer</span></span>](../../standard/analyzers/portability-analyzer.md)
