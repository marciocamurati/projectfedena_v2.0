#Fedena Heroku Fix Version : Open source school management system

Project Fedena is the open source school management system based on Ruby on Rails. It is developed by a team of developers at Foradian Technologies. The project was made open source by Foradian, and is now maintained by the open source community. Fedena is the ideal solution for schools and campuses that want an easy means to manage all campus records.

The Project Fedena website http://projectfedena.org/ is the home to the developer community behind Fedena. There you can find forums and bug tracker for Fedena.

This version have a fix to use bundle to install the gems at Heroku and some fix with binary type to PostgreSQL.

#Demo
A demo website for Fedena has been set up at demo.projectfedena.org. You can log in with following usernames and passwords:

    * As admin -- username - admin, password - admin123
    * As student -- username - 1, password - 1123
    * As employee -- username - E1, password - E1123

#License

Fedena is released under the Apache License 2.0.

#Installation

Fedena requires Ruby,Rails,MySQL and some gems installed.
Step 1: Install Ruby

   1. Download the latest One-Click Ruby Installer for Windows. (Preferably version 1.8.6)
   2. Double-click on the downloaded executable and follow the installation instructions. Unless you have some special needs, just press Enter to accept all of the defaults.

Note to Linux and OS X users: Please install rubygems from the packages.

Step 2: Install Rails

Now we can use the RubyGems package manager to download and install Rails 2.3.5(Note: Version should be 2.3.5),

   1. Open a command window and run the command gem install rails -v=2.3.5 --remote.
   2. RubyGems will also install all of the other libraries that Rails depends on. For each of these dependencies, RubyGems will ask you if you want to install it. Answer "y" (yes) to each one.

Step 3: Install MySQL

   1. Download  and install the latest "essential" version of the MySQL installer.


Step 4: Setup Fedena

   1. Download Fedena source code for GitHub. Extract the ZIP/TAR archive and save to a folder (say C:\Fedena).
   2. Now goto the fedena source directory in the command window.
   3. Run the command  rake gems:install .This will install all missing gems.
   4. Update the MySQL login details in config/database.yml
   5. Run the command  rake db:create. This will create the required databases.
   6. Run the command  rake db:migrate. This will populate the database with required tables.
   7. Finally, run the command ruby script/server .This would start the server and it will be accessible at http://localhost:3000
   
#Fedena Configurations:

 1. To enable SMS Module
            i) Add a new row with config_key = "AvailableModules" and config_value = "SMS" (without quotes,case-sensitive) of `configurations` Table
           ii) Update the SMS API settings in Libs/sms_manager.rb to use the SMS Module.
2. To disable HR module, delete the row with config_key = "AvailableModules" and config_value = "HR"
3. To disable Finance module, delete the row with config_key = "AvailableModules" and config_value = "Finance"

#Community Support:

Visit www.projectfedena.org for community support.

# Install at Heroku

Execute the commands below to install at your Heroku account:

1. git init
$Initialized empty Git repository in .git/
2. git add .
3. git commit -m "fedena heroku version"
$Created initial commit 5df2d09: fedena heroku version
xxx files changed, xxxx insertions(+), 0 deletions(-)
4. heroku create
5. git push heroku master
$Counting objects: XX, done.
Delta compression using up to 2 threads.
Compressing objects: 100% (12/12), done.
Writing objects: 100% (13/13), 7.15 KiB, done.
Total 13 (delta 6), reused 0 (delta 0)

-----> Heroku receiving push
-----> Rails app detected
-----> Gemfile detected, running Bundler version 1.0.7
       Unresolved dependencies detected; Installing...
       Fetching source index for http://rubygems.org/
       Installing rake (0.8.7) 
       Installing activesupport (2.3.5) 
       Installing rack (1.0.1) 
       Installing actionpack (2.3.5) 
       Installing actionmailer (2.3.5) 
       Installing activerecord (2.3.5) 
       Installing activeresource (2.3.5) 
       Installing declarative_authorization (0.5.2) 
       Installing prawn-core (0.6.3) 
       Installing prawn-format (0.2.3) 
       Installing prawn-layout (0.3.2) 
       Installing prawn-security (0.1.1) 
       Installing prawn (0.6.3) 
       Installing rails (2.3.5) 
       Installing searchlogic (2.4.27) 
       Using bundler (1.0.7) 
       Your bundle is complete! It was installed into ./.bundle/gems/
       Compiled slug size is 11.6MB
-----> Launching... done
       http://xxxxx.heroku.com deployed to Heroku

To git@heroku.com:xxxxx.git
   a213125..f4f09ab  master -> master
6. heroku rake db:migrate
$** Invoke db:migrate (first_time)
** Invoke environment (first_time)
** Execute environment
** Execute db:migrate
==  CreateEmployees: migrating ================================================
-- create_table(:employees)
   -> 0.0230s
==  CreateEmployees: migrated (0.0611s) =======================================

==  CreatePayrollCategories: migrating ========================================
-- create_table(:payroll_categories)
   -> 0.0097s
==  CreatePayrollCategories: migrated (0.0098s) ===============================

==  CreateEmployeeSalaryStructures: migrating =================================
-- create_table(:employee_salary_structures)
   -> 0.0082s
==  CreateEmployeeSalaryStructures: migrated (0.0083s) ========================

==  CreateMonthlyPayslips: migrating ==========================================
-- create_table(:monthly_payslips)
   -> 0.0078s
==  CreateMonthlyPayslips: migrated (0.0079s) =================================

==  CreateEmployeeLeaveTypes: migrating =======================================
-- create_table(:employee_leave_types)
   -> 0.0124s
==  CreateEmployeeLeaveTypes: migrated (0.0125s) ==============================

==  CreateEmployeeAttendances: migrating ======================================
-- create_table(:employee_attendances)
   -> 0.0077s
==  CreateEmployeeAttendances: migrated (0.0078s) =============================

==  CreateApplyLeaves: migrating ==============================================
-- create_table(:apply_leaves)
   -> 0.0135s
==  CreateApplyLeaves: migrated (0.0136s) =====================================

==  CreateEmployeesSubjects: migrating ========================================
-- create_table(:employees_subjects)
   -> 0.0078s
==  CreateEmployeesSubjects: migrated (0.0078s) ===============================

==  CreateIndividualPayslipCategories: migrating ==============================
-- create_table(:individual_payslip_categories)
   -> 0.0407s
==  CreateIndividualPayslipCategories: migrated (0.0408s) =====================

==  CreateReminders: migrating ================================================
-- create_table(:reminders)
   -> 0.0116s
==  CreateReminders: migrated (0.0117s) =======================================

==  CreateFinanceTransactionCategories: migrating =============================
-- create_table(:finance_transaction_categories)
   -> 0.0295s
==  CreateFinanceTransactionCategories: migrated (0.0506s) ====================

==  CreateFinanceTransactions: migrating ======================================
-- create_table(:finance_transactions)
   -> 0.0275s
==  CreateFinanceTransactions: migrated (0.0276s) =============================

==  CreateFinanceDonations: migrating =========================================
-- create_table(:finance_donations)
   -> 0.0397s
==  CreateFinanceDonations: migrated (0.0398s) ================================

==  CreateFinanceFeeCollections: migrating ====================================
-- create_table(:finance_fee_collections)
   -> 0.0084s
==  CreateFinanceFeeCollections: migrated (0.0085s) ===========================

==  CreateFinanceFees: migrating ==============================================
-- create_table(:finance_fees)
   -> 0.0101s
==  CreateFinanceFees: migrated (0.0102s) =====================================

==  CreateFinanceFeeStructureElements: migrating ==============================
-- create_table(:finance_fee_structure_elements)
   -> 0.0085s
==  CreateFinanceFeeStructureElements: migrated (0.0086s) =====================

==  CreatePrivileges: migrating ===============================================
-- create_table(:privileges)
   -> 0.0084s
==  CreatePrivileges: migrated (0.0806s) ======================================

==  CreatePrivilegesUsersJoinTable: migrating =================================
-- create_table(:privileges_users, {:id=>false})
   -> 0.0032s
==  CreatePrivilegesUsersJoinTable: migrated (0.0033s) ========================

==  CreateFinanceTransactionTriggers: migrating ===============================
-- create_table(:finance_transaction_triggers)
   -> 0.0130s
==  CreateFinanceTransactionTriggers: migrated (0.0131s) ======================

==  CreateEvents: migrating ===================================================
-- create_table(:events)
   -> 0.0123s
==  CreateEvents: migrated (0.0124s) ==========================================

==  CreateBatchEvents: migrating ==============================================
-- create_table(:batch_events)
   -> 0.0084s
==  CreateBatchEvents: migrated (0.0085s) =====================================

==  CreateEmployeeDepartmentEvents: migrating =================================
-- create_table(:employee_department_events)
   -> 0.0089s
==  CreateEmployeeDepartmentEvents: migrated (0.0089s) ========================

==  CreateStudentAdditionalDetails: migrating =================================
-- create_table(:student_additional_details)
   -> 0.0085s
==  CreateStudentAdditionalDetails: migrated (0.0086s) ========================

==  CreateStudentAdditionalFields: migrating ==================================
-- create_table(:student_additional_fields)
   -> 0.0081s
==  CreateStudentAdditionalFields: migrated (0.0081s) =========================

==  CreateLiabilities: migrating ==============================================
-- create_table(:liabilities)
   -> 0.0131s
==  CreateLiabilities: migrated (0.0131s) =====================================

==  CreateAssets: migrating ===================================================
-- create_table(:assets)
   -> 0.0122s
==  CreateAssets: migrated (0.0123s) ==========================================

==  CreatePeriodEntries: migrating ============================================
-- create_table(:period_entries)
   -> 0.0085s
==  CreatePeriodEntries: migrated (0.0085s) ===================================

==  CreateWeekdays: migrating =================================================
-- create_table(:weekdays)
   -> 0.0117s
==  CreateWeekdays: migrated (0.0371s) ========================================

==  CreateFinanceFeeCategories: migrating =====================================
-- create_table(:finance_fee_categories)
   -> 0.0234s
==  CreateFinanceFeeCategories: migrated (0.0234s) ============================

==  CreateFinanceFeeParticulars: migrating ====================================
-- create_table(:finance_fee_particulars)
   -> 0.0283s
==  CreateFinanceFeeParticulars: migrated (0.0284s) ===========================

==  CreateSmsSettings: migrating ==============================================
-- create_table(:sms_settings)
   -> 0.0077s
==  CreateSmsSettings: migrated (0.0429s) =====================================

==  CreateElectives: migrating ================================================
-- create_table(:electives)
   -> 0.0230s
==  CreateElectives: migrated (0.0230s) =======================================

==  StudentsSubject: migrating ================================================
-- create_table(:students_subjects)
   -> 0.0084s
==  StudentsSubject: migrated (0.0085s) =======================================

==  CreateGroupedExams: migrating =============================================
-- create_table(:grouped_exams)
   -> 0.0078s
==  CreateGroupedExams: migrated (0.0079s) ====================================

==  CreateArchivedEmployees: migrating ========================================
-- create_table(:archived_employees)
   -> 0.0306s
==  CreateArchivedEmployees: migrated (0.0306s) ===============================

==  CreateArchivedEmployeeSalaryStructures: migrating =========================
-- create_table(:archived_employee_salary_structures)
   -> 0.0248s
==  CreateArchivedEmployeeSalaryStructures: migrated (0.0249s) ================

==  CreateArchivedEmployeeBankDetails: migrating ==============================
-- create_table(:archived_employee_bank_details)
   -> 0.0090s
==  CreateArchivedEmployeeBankDetails: migrated (0.0091s) =====================

==  CreateArchivedEmployeeAdditionalDetails: migrating ========================
-- create_table(:archived_employee_additional_details)
   -> 0.0088s
==  CreateArchivedEmployeeAdditionalDetails: migrated (0.0089s) ===============

==  CreateStudentPreviousDatas: migrating =====================================
-- create_table(:student_previous_datas)
   -> 0.0141s
==  CreateStudentPreviousDatas: migrated (0.0142s) ============================

==  CreateStudentPreviousSubjectMarks: migrating ==============================
-- create_table(:student_previous_subject_marks)
   -> 0.0231s
==  CreateStudentPreviousSubjectMarks: migrated (0.0232s) =====================

==  CreateXmls: migrating =====================================================
-- create_table(:xmls)
   -> 0.0130s
==  CreateXmls: migrated (0.0465s) ============================================

==  CreateArchivedExamScores: migrating =======================================
-- create_table(:archived_exam_scores)
   -> 0.0089s
==  CreateArchivedExamScores: migrated (0.0089s) ==============================

==  CreateAdditionalExamGroups: migrating =====================================
-- create_table(:additional_exam_groups)
   -> 0.0125s
==  CreateAdditionalExamGroups: migrated (0.0126s) ============================

==  CreateAdditionalExams: migrating ==========================================
-- create_table(:additional_exams)
   -> 0.0100s
==  CreateAdditionalExams: migrated (0.0101s) =================================

==  CreateAdditionalExamScores: migrating =====================================
-- create_table(:additional_exam_scores)
   -> 0.0093s
==  CreateAdditionalExamScores: migrated (0.0093s) ============================

** Invoke db:schema:dump (first_time)
** Invoke environment 
** Execute db:schema:dump

