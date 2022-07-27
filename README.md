
# LaTeX 

## LaTeX это?
LaTEX (произносится как «лэйтех» или «латех») представляет собой инструмент для создания документов. 

## Нужен для?
Этот инструмент используется для создания научных документов, написания книг, а также многих других форм публикаций. Он дает пользователям возможность очень быстро реализовывать такие элементы печатного набора, как математические выражения, таблицы, ссылки и библиографии, получая согласованную разметку по всем разделам.

## Начало
Работать удобнее всего в онлайн редакторе __Overleaf__, который позволяет нескольким пользователям редактировать один и тот же документ одновременно и просматривать изменения друг друга в режиме реального времени. Программа поддерживает практически все функции LaTeX.

Overleaf также содержит огромное количество шаблонов различных форматов (презентации, статьи, проекты, исследование и тд). 
Для начала создадим новый пустой проект:

1. New project => Blank project, задаем название проекту и Create.
2. Сразу появляется структура и задается тип документа:

      `\documentclass{article} `    <= документ класса статья
      
   Также автоматически заполняются поля title, date, author ... - для титульного листа (такая структура зашита в классе article по умолчанию)

![image](https://user-images.githubusercontent.com/78480759/181357593-14f270cc-46c2-4edf-8b1f-b3b655ddb4b3.png)

Однако, можно и самостоятельно оформить титульный лист, содержание и сделать любое оформление листа) 

3. Чтобы документ заполнился правилньо, существует определенная структура, а именно наличие глобального блока `\begin{document}` `\end{document}`
Это тело документа, в котором будут производиться различные махинации с текстом. (##### оно обязательно должно присутствовать в коде)

Все, что содержится в файле .tex до `\begin{document}`, называется __преамбулой__. В ней можно определить тип создаваемого документа, используемый язык, нужные библиотеки и ряд других элементов. 

## Основные операции 

1. Оставление комментариев в коде происходит с помощью символа % (либо комбинация клавиш Ctrl+/)
2. Форматирование текста:

      2.1 __Жирный__  (`\textbf{your text}`)
     
      2.2 _Курсив_ (`\textit{your text}`)
     
      2.3 <u> Подчеркнутый </u>  (`\underline{your text}`)
   
   `\usepackage[usenames]{color}` пакет для работы с цветным текстом
   Например, `\textbf{\textcolor[rgb]{1.00,0.00,0.00}{Каждый}` выведет слово "Каждый" красным шрифтом
     
3. Размер шрифта: (формат написания `\small{you text}` )
      
      `\footnotesize` < `\small` < `\normalsize` (Размер основного текста) < `\large` == `\Large` < `\LARGE` < `\huge` == `\Huge`
     
4. Выравнивание текста по центру, левой и правой сторонам

    `\begin{center}`
      Выравнивание по центру
     `\end{center}`

      `\begin{flushright}`
       Выравнивание по правому краю
      `\end{flushright}`
      
      `\begin{flushleft}`
        Выравнивание по левому краю
       `\end{flushleft}`
       
4. `\vspace{5mm}` - вертикальный отступ 5mm
5. `\hspace{5mm}` - горизонтальный отступ 5mm
6. `\newline` — переход на новую строку внутри одного абзаца, предыдущая строка не растягивается. Равнозначно вместо этого использовать знак \\ 
   `\linebreak` — переход на новую строку внутри абзаца, предыдущая строка растягивается по ширине.
   `\pagebreak` — переход на новую страницу, предыдущая растягивается
   `\newpage` — переход на новую страницу
 
 7. Линии разной толщины `\rule{35mm}{.3pt}` и `\rule{35mm}{3pt}`
 8. `\tableofcontents` — создает содержание
 9. `\section*{Заголовок}`
    `\addcontentsline{toc}{section}{Заголовок добавить в содержание}
    `\subsection{Подзаголовок раздела с номером}`
    `\setcounter{subsection}{3}`
    `\subsubsection{Подподзаголовок раздела с номером}`
    
  10. Для набора формул используют знак $. Если строка заканчивается знаком =, +, −, или подобным, то знак нужно продублировать и на следующей строке. Для этого      используют команду \hm, например, из $y(x)=x^2\hm-2x\hm+3$

  11. Для создания таблицы используется структура 
      `\begin{tabular}{c|r|l}`
      `\end{tabular}`
      
      где {c|r|l} отвечает за выравнивание каждого столбца по центру, справа, слева соответственно, а | рисует вертикальные линии между стоблцов
      `\hline` чертит линию между строками
      `\cline{2-4}` черта только между 2-4 столбцами
      `\multicolumn{8}{c}{Текст}` - объединение ячеек нескольких столбцов ( объединены 9 ячеек, текст выровнен по центру, границ нет)
      `\raisebox{1.5ex}[0cm][0cm]{Текст}` позволяет текст в объединенных строках выровнять по середине
      
  12. Списки
        1. Нумерованные 
            
            `\begin{itemize}
                \item
                \item ...
             \end{itemize}`
            
        3. Маркированные
              
            `\begin{enumerate}
                  \item 
                  \item ...
              \end{enumerate}`
              
        5. Вложенные
        
            `\begin{itemize}
                \item
                \begin{enumerate}
                  \item 
                  \item ...
                \end{enumerate}
             \end{itemize}`
             
  13. Картинки 
    
   Необходимо подключить в преамбуле проекта пакет`\usepackage{graphicx}`

  `\includegraphics[scale=0.7]{Путь к файлу/имя рисунка.eps}`  (scale=0.7 означает, что размер рисунка будет равен 70% от реального размера)
  
  14. Ссылка на литературу
        
        `\cite{метка книги}` - делается ссылка на источник/литературу, полное описание истоника располагается автоматически в конце документа с соответствующим в тексте номером
        
   15. `\renewcommand{\раздел который хотим переименовать}{\Название}` можно изменить название ключевых разделов документа как содержание, библиография и тд.
      
      
