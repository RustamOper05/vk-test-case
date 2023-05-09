# Тестовое задание в VK CORE ML
Задача:
Необходимо построить векторные представления (эмбеддинги) пользователей и фильмов используя нейросетевые подходы, чтобы можно было по эмбеддингу пользователя искать похожие эмбеддинги фильмов и рекомендовать ему их.

## Данные:
https://grouplens.org/datasets/movielens/latest/ - 
lатасет представляет из себя данные интеракций пользователей и фильмов. В датасете присутствуют 27 000 000 оценок к 58 000 фильмам от 280 000 пользователей.
| userId | movieId | rating | timestamp |      title |                                           genres | nDCG@5 |
|-------:|--------:|-------:|----------:|-----------:|-------------------------------------------------:|--------|
|      0 |       1 |    307 |       3.5 | 1256677221 | Three Colors: Blue (Trois couleurs: Bleu) (1993) |  Drama |
|      1 |       6 |    307 |       4.0 |  832059248 | Three Colors: Blue (Trois couleurs: Bleu) (1993) |  Drama |
|      2 |      56 |    307 |       4.0 | 1383625728 | Three Colors: Blue (Trois couleurs: Bleu) (1993) |  Drama |
|      3 |      71 |    307 |       5.0 | 1257795414 | Three Colors: Blue (Trois couleurs: Bleu) (1993) |  Drama |
|      4 |      84 |    307 |       3.0 |  999055519 | Three Colors: Blue (Trois couleurs: Bleu) (1993) |  Drama |

## Решение:
Для решения задачи была использована архитектура neural collaborative filtering
![image](https://github.com/RustamOper05/vk-test-case/assets/88241357/b3518548-6932-4b98-96c9-fc6e97fd2e72)

## Валидация:
Сравнение метрик качества рекомендаций модели и константных рекомендаций "самое популярное"
| Model    | MAP@10 | HR@10 | P@10 | R@10 | F1@K |
|----------|--------|-------|------|------|------|
| NCF      |    0.22|0.380  |0.339 | 0.159|0.217 |
| Constant |    0.23|0.040  |0.200 |0.025 |0.044 |
