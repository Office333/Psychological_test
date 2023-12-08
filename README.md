# Psychological_test
class PsychologicalTest:
    def __init__(self, questions):
        self.questions = questions
        self.answers = []

    def administer_test(self):
        print("請回答以下問題（1表示完全不同意，5表示完全同意）：")
        for i, question in enumerate(self.questions, start=1):
            answer = input(f"{i}. {question} ")
            self.answers.append(int(answer))

    def calculate_score(self):
        total_score = sum(self.answers)
        return total_score

    def interpret_results(self, total_score):
        print("測驗結果：")
        if total_score < 20:
            print("你可能傾向於不同意的方向。")
        elif total_score >= 20 and total_score < 40:
            print("你的態度相對中立。")
        else:
            print("你可能傾向於同意的方向。")

if __name__ == "__main__":
    # 測試問題
    questions = [
        "我喜歡嘗試新的事物。",
        "我通常感到輕鬆愉快。",
        "我容易感到焦慮或緊張。",
        "我喜歡與人交往。",
        "我喜歡解決問題。",
    ]

    # 創建測驗
    test = PsychologicalTest(questions)

    # 進行測驗
    test.administer_test()

    # 計算分數
    total_score = test.calculate_score()

    # 解釋結果
    test.interpret_results(total_score)
