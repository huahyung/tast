# tast
from PyQt5.QtCore import Qt
from PyQt5.QtWidgets import QApplication, QLineEdit, QWidget, QVBoxLayout, QPushButton, QLabel

from instr import *  
from final_win import *
class TestWin(QWidget):
    def __init__(self):
        super().__init__()
        self.set_appear() # устанавливает, как будет выглядеть окно
        self.initUI() # создаём и настраиваем графические элементы
        self.connects() # устанавливает связи между элементами
        self.show()  # показываем окно
    def set_appear(self):
        self.setWindowTitle(txt_title)
        self.resize(win_width, win_height)
        self.move(win_x, win_y)
    def initUI(self):
        self.namevod = QLabel(txt_hintname)
        self.namevodt = QLineEdit()
        self.age = QLabel(txt_hintage)
        self.aget = QLineEdit()
        self.test1 = QLabel(txt_test1)
        self.test11 = QPushButton(txt_starttest1)
        self.test111 = QLineEdit(txt_hinttest1)
        self.test2 = QLabel(txt_test2)
        self.test22 = QPushButton(txt_starttest2)
        self.test222 = QLineEdit(txt_hinttest2)
        self.test3 = QLabel(txt_test3)
        self.test33 = QPushButton(txt_starttest3)
        self.test333= QLineEdit(txt_hinttest3)
        self.timer = QLabel('таймер')

        self.btn_next = QPushButton(txt_sendresults)
        
        self.layout = QVBoxLayout()
        self.layout.addWidget(self.namevod, alignment= Qt.AlignLeft)
        self.layout.addWidget(self.namevodt, alignment= Qt.AlignLeft)
        self.layout.addWidget(self.age, alignment= Qt.AlignLeft)
        self.layout.addWidget(self.aget, alignment= Qt.AlignLeft)
        self.layout.addWidget(self.test1, alignment= Qt.AlignLeft)
        self.layout.addWidget(self.test11, alignment= Qt.AlignLeft)
        self.layout.addWidget(self.test111, alignment= Qt.AlignLeft)
        self.layout.addWidget(self.test2, alignment= Qt.AlignLeft)
        self.layout.addWidget(self.test22, alignment= Qt.AlignLeft)
        self.layout.addWidget(self.test222, alignment= Qt.AlignLeft)
        self.layout.addWidget(self.test3, alignment= Qt.AlignLeft)
        self.layout.addWidget(self.test33, alignment= Qt.AlignLeft)
        self.layout.addWidget(self.test333, alignment= Qt.AlignLeft)
        self.layout.addWidget(self.timer, alignment= Qt.AlignRight)
        self.layout.addWidget(self.btn_next)
       
        self.setLayout(self.layout)
    def next_click(self):
        self.hide()
        self.fw = FinalWin()
    def connects(self):
        self.btn_next.clicked.connect(self.next_click)

app = QApplication([])
tw = TestWin()
app.exec_()
