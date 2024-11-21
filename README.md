Перше ніж запускати імпортуйте БД із файлу MedHelperDb.bak, MedHelperDb.bacpac або MedHelperDb.mdf

Основна структура проєкту: 
MedHelper:
	Controllers (Окрема директорія для глобальних змінних та функцій):
		GlobalFunctions.cs (містить зібраний глобальний функціонал проєкту)
		GlobalVariables.cs (містить зібрані глобальні змінні проєкту для проміжного зв'язку)
	Models (Директорія що містить опис сутностей для зв'язку з БД):
		Account.cs (Модель для представлення облікового запису користувача)
		Client.cs (Модель для представлення клієнта/пацієнта)
		Disease.cs (Модель для представлення хвороби)
		Diseases_Treatments.cs (Проміжна модель зв'язку між сутностями Хвороб та Лікувань)
		Doctor.cs (Модель для представлення доктора)
		Favourite.cs (Модель для представлення списку обраних хвороб)
		Medicine.cs (Модель для представлення медикаменту)
		MyModels.cs (Загальна модель що містить зв'язок із БД на основі DbSet (представляє колекцію всіх сутностей у контексті або які можуть бути запитані з бази даних заданого типу) 
		та утворює набір інших зв'язаних моделей)
		Treatment.cs (Модель для представлення списку лікування)
	Sources (Директорія для класів із повторюваним кодом стилів):
		Styles.cs (Клас для зберігання повторюваного коду стилів)
	Views (Усі представлення (Views) та елементи управління (UserControls) для виведення на екран):
		AboutUC.cs
		AIContainerUC.cs
		AIHelperUC.cs
		AIResUC.cs
		DiseasesUC.cs
		FavouriteUC.cs
		InfoDiseaseUC.cs
		InfoTreatmentUC.cs
		LoginUC.cs
		MainBodyUC.cs
		MainView.cs
		SignupUC.cs
		TreatmentsUC.cs
	App.config (особливості налаштування та під'єднання БД)
	packages.config (під'єднання пакетів до проєкту)
	Program (точка запуску)

	Кожне представлення (View) в свою чергу поділяється на partial класи, наприклад:
	AboutUC.Designer.cs
	AboutUC.cs
