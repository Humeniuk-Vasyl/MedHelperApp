Перше ніж запускати імпортуйте БД із файлу MedHelperDb.bak, MedHelperDb.bacpac

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
		AboutUC.cs (Елемент управління (надалі ЕУ) який показую коротку інформацію про власника проєкту)
		AIContainerUC.cs (ЕУ-контейнер, що містить в собі AIHelperUC та AIResUC описані далі)
		AIHelperUC.cs (ЕУ AI помічника, що містить саму UI-частину цього вікна, тобто кнопки що оновлюються при виборі сценаріїв та частково їх логіку роботи і переходів)
		AIResUC.cs (ЕУ результату наданаго помічником, що містить поле для виводу тексту результату та кнопки Back й BackToMain та частково логіку роботи кнопок і переходів)
		DiseasesUC.cs (ЕУ із списком хворобами, полем для пошуку, кнопками добавлення матеріалу в обрані AddToFavourite, повернення на головне вікно Back, перегляду хвороби View та кнопками Add та Delete доступних лише лікарям)
		FavouriteUC.cs (ЕУ із списком лікувань, полем для пошуку, кнопками повернення на головне вікно Back, перегляду хвороби View та кнопками Add та Delete доступних лише лікарям)
		InfoDiseaseUC.cs (ЕУ із хворобою,Написом назви, Полями вивиду короткого опису, довгого опису та зв'язаних лікувань та медикаментів якщо такі присутні а також кнопками добавлення матеріалу в обрані AddToFavourite, повернення на головне вікно Back та кнопкою Update доступною лише лікарям)
		InfoTreatmentUC.cs (ЕУ із лікуванням, Написом назви, Полями вивиду короткого опису, опису зв'язаних хвороб та медикаментів якщо такі присутні а також кнопками повернення на головне вікно Back та кнопкою Update доступною лише лікарям)
		LoginUC.cs (ЕУ для проведення автентифікації де знаходиться поле вводу імені, паролю та функціональної кнопки Log in)
		MainBodyUC.cs (ЕУ основного вікна, де знаходиться привітання користувача, поле для пошуку, адаптивний список хвороб та лікувань, кнопка додавання хвороби в обрані AddToFavourite та перегляду хвороби/лікування View)
		MainView.cs (Вікно - контейнер для всіх інших вікон включно з MainBodyUC? де знаходиться догіка обробки переходів між ними та інший функціонал що можно переглянути в самому файлі MainView)
		SignupUC.cs (ЕУ для проведення реєстрації із валідацією даних для цього, де знаходиться поле вводу імені, паролю, повторного паролю, номеру телефону та функціональної кнопки Sign Up)
		TreatmentsUC.cs (ЕУ із списком лікувань, полем для пошуку, кнопками повернення на головне вікно Back, перегляду лікування View та кнопками Add та Delete доступних лише лікарям)
	App.config (особливості налаштування та під'єднання БД)
	packages.config (під'єднання пакетів до проєкту)
	Program (точка запуску)





	Кожне представлення (View) Або ЕУ (Елемент управління - User Control - US) в свою чергу поділяються на partial класи, наприклад:
	AboutUC.Designer.cs
	AboutUC.cs

	Кожне View Або US поділені на регіони region для зручного провдення перевірок та структуровано представлення коду, наприклад для MainView.cs:
	
	
	#region MainBtnsClick
	... Code ...
	#endregion

	#region MainOperations
	...
	#endregion

	#region MainSpecOperations
	...
	#endregion

	Функціональні особливості кнопок, переходів, обробки вмісту ЕУ, валідацій, зміни станів та подій описані безпосередньо в відповідних ЕУ та View
