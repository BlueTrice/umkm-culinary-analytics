# TASK_LIST.md (MVP)

> **Aturan umum** - Satu task = satu file. - Satu prompt Claude = satu
> task. - Jangan lanjut sebelum file berhasil dibuat. - Selalu gunakan
> `PROJECT_SPEC.md` sebagai acuan.

  -------------------------------------------------------------------------------------------------------
  ID             Folder                        File                        Tujuan         Depends
  -------------- ----------------------------- --------------------------- -------------- ---------------
  BE-001         app/core                      config.py                   Konfigurasi    \-
                                                                           aplikasi       

  BE-002         app/database                  database.py                 Koneksi        BE-001
                                                                           SQLAlchemy     

  BE-003         app/core                      security.py                 JWT & Password BE-001
                                                                           Hash           

  BE-004         app/core                      dependencies.py             Dependency     BE-002,BE-003
                                                                           FastAPI        

  BE-005         app                           main.py                     Entry point    BE-001..004
                                                                           FastAPI        

  BE-006         app/models                    store.py                    Model Store    BE-002

  BE-007         app/models                    user.py                     Model User     BE-006

  BE-008         app/models                    menu.py                     Model Menu     BE-006

  BE-009         app/models                    transaction.py              Model          BE-006,007
                                                                           Transaction    

  BE-010         app/models                    transaction_item.py         Model          BE-009,008
                                                                           Transaction    
                                                                           Item           

  BE-011         app/schemas                   user.py                     Schema User    BE-007

  BE-012         app/schemas                   menu.py                     Schema Menu    BE-008

  BE-013         app/schemas                   transaction.py              Schema         BE-009,010
                                                                           Transaction    

  BE-014         app/repositories              user_repository.py          Repository     BE-007
                                                                           User           

  BE-015         app/repositories              menu_repository.py          Repository     BE-008
                                                                           Menu           

  BE-016         app/repositories              transaction_repository.py   Repository     BE-009
                                                                           Transaction    

  BE-017         app/services                  auth_service.py             Login Service  BE-014

  BE-018         app/services                  menu_service.py             Menu Service   BE-015

  BE-019         app/services                  transaction_service.py      Transaction    BE-016
                                                                           Service        

  BE-020         app/services                  dashboard_service.py        Dashboard      BE-016
                                                                           Service        

  BE-021         app/services                  export_service.py           Export         BE-016
                                                                           CSV/XLSX       

  BE-022         app/api                       auth.py                     Login API      BE-017

  BE-023         app/api                       menu.py                     Menu API       BE-018

  BE-024         app/api                       users.py                    Employee API   BE-014

  BE-025         app/api                       transactions.py             Transaction    BE-019
                                                                           API            

  BE-026         app/api                       dashboard.py                Dashboard API  BE-020

  BE-027         app/api                       export.py                   Export API     BE-021

  FE-001         src/services                  api.ts                      Axios Instance \-

  FE-002         src/router                    index.tsx                   Router         FE-001

  FE-003         src/layouts                   DashboardLayout.tsx         Layout         FE-002

  FE-004         src/pages/auth                LoginPage.tsx               Login Page     FE-001

  FE-005         src/components/auth           LoginForm.tsx               Login Form     FE-004

  FE-006         src/components/layout         Sidebar.tsx                 Sidebar        FE-003

  FE-007         src/components/layout         Header.tsx                  Header         FE-003

  FE-008         src/pages/dashboard           DashboardPage.tsx           Dashboard      FE-006,FE-007

  FE-009         src/services                  authService.ts              Auth API       FE-001

  FE-010         src/pages/menu                MenuPage.tsx                Menu Page      FE-001

  FE-011         src/components/menu           MenuTable.tsx               Table Menu     FE-010

  FE-012         src/components/menu           MenuForm.tsx                Form Menu      FE-010

  FE-013         src/services                  menuService.ts              Menu API       FE-001

  FE-014         src/pages/users               EmployeePage.tsx            Pegawai        FE-001

  FE-015         src/components/users          EmployeeTable.tsx           Table Pegawai  FE-014

  FE-016         src/components/users          EmployeeForm.tsx            Form Pegawai   FE-014

  FE-017         src/pages/transactions        TransactionPage.tsx         Halaman        FE-001
                                                                           Transaksi      

  FE-018         src/components/transactions   MenuSelector.tsx            Pilih Menu     FE-017

  FE-019         src/components/transactions   Cart.tsx                    Keranjang      FE-017

  FE-020         src/components/transactions   PaymentForm.tsx             Payment        FE-017

  FE-021         src/services                  transactionService.ts       API Transaksi  FE-001

  FE-022         src/pages/history             HistoryPage.tsx             Riwayat        FE-001

  FE-023         src/components/history        HistoryTable.tsx            Tabel Riwayat  FE-022

  FE-024         src/components/history        TransactionDetail.tsx       Detail         FE-022

  FE-025         src/pages/export              ExportPage.tsx              Export         FE-001

  FE-026         src/services                  exportService.ts            API Export     FE-001

  FE-027         src/components/dashboard      RevenueCard.tsx             Revenue Card   FE-008

  FE-028         src/components/dashboard      TransactionCard.tsx         Transaction    FE-008
                                                                           Card           

  FE-029         src/components/dashboard      ItemCard.tsx                Item Card      FE-008

  FE-030         src/components/dashboard      TopMenuCard.tsx             Top Menu Card  FE-008
  -------------------------------------------------------------------------------------------------------

## Setelah FE-030

-   Integrasi dan pengujian.
-   Deploy backend.
-   Deploy frontend.
-   Uji di UMKM.
