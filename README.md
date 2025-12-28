-Toolkit in stile XP Manager per Windows 11: moduli cosmetici e di tweak guidato con preset Safe/Advanced, log e (dove possibile) undo tramite punto d
i ripristino.
+Toolkit in stile XP Manager per Windows 11: moduli cosmetici e di tweak guidato con preset Safe/Advanced, log e undo quando possibile tramite punto d
i ripristino.
     
## Stack
-- .NET 6 + WPF (WinUI 3 migrabile quando disponibile sui template ocali).
-- MVVM leggero, backend modulare richiamato via PowerShell wrapper.     +Usa .NET 6 con WPF (WinUI 3 migrabile appena i template sono disponibili), architettura MVVM leggera e backend modulare richiamato tramite wrapper Po
werShell.
     
## Moduli pianificati
 10 -- SystemOverview, CleanupCenter, StartupManager, ServiceTuner, AppManager, DriverAndUpdate, PrivacyGuard, NetworkTools, PerformanceBoost, StorageTool
 s, BackupRestore, ContextMenuEditor, FirewallRules, TaskSchedulerLite, SystemInfoExport.
 9 +SystemOverview, CleanupCenter, StartupManager, ServiceTuner, AppManager, DriverAndUpdate, PrivacyGuard, NetworkTools, PerformanceBoost, StorageTools,
 BackupRestore, ContextMenuEditor, FirewallRules, TaskSchedulerLite, SystemInfoExport.

 ## Struttura progetto
 -- `Win11ProManager.App`: UI WPF (Views, ViewModels, Models, Services), preset Safe/Advanced, shell di navigazione.
 -- `Win11ProManager.Core`: interfacce modulo (`IModuleAction`, `ModuleResult`), futuri wrapper PowerShell e logica condivisa.
 -- `scripts/`: da aggiungere per build, pack MSIX o portable.
 +`Win11ProManager.App` contiene la UI WPF (Views, ViewModels, Models, Services), i preset Safe/Advanced e la shell di navigazione.
 +`Win11ProManager.Core` espone le interfacce modulo (`IModuleAction`, `ModuleResult`), i futuri wrapper PowerShell e la logica condivisa.
 +`scripts/` sarà aggiunta per build, pack MSIX o portable.

 ## Stato attuale
 -- Shell UI con navigation, header, area azioni e lista moduli seed.
 -- ViewModel base (`MainViewModel`) con definizioni modulo e azioni; placeholder `PowerShellService`.
 -- Soluzione `Win11ProManager.sln` con App e Core referenziati; build OK. 
 +Shell UI con navigation, header, area azioni e lista moduli seed.
 +ViewModel base (`MainViewModel`) con definizioni dei moduli e azioni; placeholder `PowerShellService`.
 +Soluzione `Win11ProManager.sln` con App e Core referenziati; build completata correttamente.

 ## Requisiti locali
 -- dotnet SDK 6 (installato). Se aggiorni al SDK 8: modifica i `TargetFramework` a net8.0-windows e net8.0.
 -- Windows 11.
 +dotnet SDK 6 installato (se passi a SDK 8 aggiorna i `TargetFramework` a net8.0-windows e net8.0).
 +Windows 11.
  
 
   
    
 ## Suggeriti prossimi passi
 34 -1) Collegare il bottone "Apri modulo" a viste dedicate per Cleanup/Startup/Privacy (UI base dei moduli).
 35 -2) Implementare `PowerShellService` con log, undo (restore point), preset Safe/Advanced e storage config in `%AppData%/Win11ProManager`.
 36 -3) Aggiungere `LoggerPanel` in UI e persistenza log rotante.
 37 -4) Considerare migrazione a WinUI 3 quando i template sono disponibili.
 33 +Collegare il bottone "Apri modulo" a viste dedicate per Cleanup, Startup e Privacy.
 34 +Implementare `PowerShellService` con log, undo (restore point), preset Safe/Advanced e storage config in `%AppData%/Win11ProManager`.
 35 +Aggiungere `LoggerPanel` in UI e persistenza log rotante.
 36 +Considerare la migrazione a WinUI 3 quando i template saranno disponibili.
 37
 38  ## Git e pubblicazione
 40 -- Inizializza: `git init && git add . && git commit -m "chore: scaffold Win11ProManager v0.2"`.
 41 -- Repo consigliata: `Win11ProManager` o `windows11-pro-manager`.
 42 -- Remote: `git remote add origin git@github.com:<utente>/Win11ProManager.git` poi `git push -u origin main`.
 39 +Inizializza con `git init && git add . && git commit -m "chore: scaffold Win11ProManager v0.2"`.
 40 +Nome repo consigliato: `Win11ProManager` oppure `windows11-pro-manager`.
    41 +Aggiungi remote: `git remote add origin git@github.com:<utente>/Win11ProManager.git` poi `git push -u origin main`.
