Ход работы: 
1. Форк репозитория Kotlin-Polytech/KotlinAsFirst2020 на GitHub
2. Клонирование форка
	git clone https://github.com/irreiku/KotlinAsFirst2020
	cd KotlinAsFirst2020
3. Добавление репозитория irreiku/KotlinAsFirst2021 в качестве upstream-my
	git remote add upstream-my https://github.com/irreiku/KotlinAsFirst2021
	git fetch upstream-my
	git remote -v
4. Создание ветки backport и перенос в нее моих коммитов
	git checkout -b backport
	git cherry-pick d535f359...FETCH_HEAD
5. Добавление репозитория ssassha/KotlinAsFirst2021 в качестве upstream-theirs
	git remote add upstream-theirs https://github.com/ssassha/KotlinAsFirst2021
	git fetch upstream-theirs
	git remote -v
6. Мердж моих решений и решений напарника в ветку master и исправление конфликтов слияния
	git checkout master
	git merge backport upstream-theirs/master
	git status
	git add -A
	git merge --continue
7. Экспорт апстримов в файл remotes
	git remote -v > remotes
	git add .\remotes
8. Создание файла howto.md с описанием хода работы
	git add .\howto.md
9. Пуш
	git push origin master

	

          


