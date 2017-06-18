#include <iostream>
#include <cstdlib>
#include <ctime>
#include <cmath>
#include <iomanip>

using namespace std;

class ExamRecord
{
	public:
		void indivStudent(int i);
		void OutputScore();
		char Grade(double average_score);
		double GetAverage();
	private:
		int idNumber;
		int score[3];
		double average;
		char grade;
};

void OutputHeader();
void SortAverage(ExamRecord allStudent[], int size);
void swap(ExamRecord& aRecord, ExamRecord& bRecord);

int main(){
	ExamRecord student[20];
	int i, j, size = 20;
	
	srand(time(0));
	
	for(i = 0 ; i < 20 ; i++)
	{
		student[i].indivStudent(i); 
	}
	
	OutputHeader();
	
	for(i = 0 ; i < 20 ; i++)
	{
		student[i].OutputScore(); 
	}
	
	cout << "Sort the score : " << endl;
	
	SortAverage(student, size);
	
	OutputHeader();
	
	for(i = 0 ; i < 20 ; i++)
	{
		student[i].OutputScore();
	}

    return 0;
}

void OutputHeader()
{
	cout << "idNumber  " << "score 1" << " score 2" << " score 3" << " Average" << " Grade" << endl;
}

void ExamRecord::indivStudent(int i)
{
	idNumber = 103 * 100 + i;
	score[0] = (rand( ) % 100);
	score[1] = (rand( ) % 100);
	score[2] = (rand( ) % 100);
	average = (score[0] + score[1] + score[2]) / 3;
	grade = Grade(average);
}

double ExamRecord::GetAverage()
{
	return score[0];
}

char ExamRecord::Grade(double average_score)
{
	if(average_score >= 90 && average_score <= 100)	
		return 'A';
	if(average_score >= 80 && average_score < 90)	
		return 'B';
	if(average_score >= 70 && average_score < 80)	
		return 'C';
	if(average_score >= 60 && average_score < 70)	
		return 'D';
	if(average_score < 60)	
		return 'F';
}

void ExamRecord::OutputScore() 
{
	cout << setw(6) << idNumber 
		 << setw(8) << score[0]
		 << setw(8) << score[1] 
		 << setw(8) << score[2]
		 << setw(8) << average
		 << setw(7) << grade << endl;
}

void SortAverage(ExamRecord allStudent[], int size) {
	int i, j, pos;

	for(i = size; i > 1; i--) {
		pos = 0;
		for(j = 1; j < i; j++) 
			if(allStudent[pos].GetAverage() < allStudent[j].GetAverage()) 
				pos = j;
		swap(allStudent[i - 1], allStudent[pos]);
	} 
}
	
void swap(ExamRecord& aRecord, ExamRecord& bRecord) {
	ExamRecord tempRecord;

	tempRecord = aRecord;
	aRecord = bRecord;
	bRecord = tempRecord;	
}
