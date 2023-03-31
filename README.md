*******************************************************************************
 * AUTHORS      : Micheal Okey-okoro
 * STUDENT IDs  : 1246538
 * Assignment#4 : New Salary Calculator
 * CLASS        : CS1A
 * SECTION      : Monday & Wednesday 8:00AM - 10:20 AM
 * DUE DATE     : 10/25/2022
 *******************************************************************************/

#include <iostream>
#include <iomanip>
using namespace std;

/*******************************************************************************
 *  Salary Calculator
 *_____________________________________________________________________________
*This program will obtain from the user the a full name, a current annual salary
*and a percent increase due on that salary. Assume that the new pay rate should
*and have been in effect on January 1, and it is now July 1. Calculate, store,
*and output the new annual salary,the new monthly salary, and the retroactive
*and pay due. Retroactive pay is the difference between what they should have
*and received had they gotten their raise on Jan. 1 and what
*and they did receive. See the Expected Input & Output for test cases and proper
formatting.
 *_____________________________________________________________________
 *  INPUT:
 *      userName           : The user's name
 *      currentAnnualSalary: The current salary
 *      payIncreaseRate    : The increase rate of pay
 *
 *  OUTPUT:
 *       newSalary         : The new salary
 *       newMonthlysalary  : The new monthly pay
 *       retroPay          : The retroactive pay
*************************************************************************/

int main()
{
/*******************************************************************************
* CONSTANTS
* -------------------------------------------------------------------------
*  * OUTPUT - USED FOR CLASS HEADING
* -------------------------------------------------------------------------
* PROGRAMMER     : Micheal Okey-okoro
* Class          : CS1A
* SECTION        : M & W 8:00am - 10:20am
* ASSIGNMENT_NUM : 11
* LAN_NAME       : New Salary Calculator
*
* -------------------------------------------------------------------------
*  * OUTPUT - USED FOR FORMATTING
* -------------------------------------------------------------------------
* months        : The amount of months in a year that the user is getting paid.
* PROMPT_COL    : The Column size for the prompts.
* HEADING_COL   : The Heading size for the columns.
* NAME SIZE
*******************************************************************************/

const char PROGRAMMER[] = "Micheal Okey-okoro";
const char CLASS[] = "CS1A";
const char SECTION[] = "M & W 8:00am - 12:20AM";
const char ASSIGNMENT_NAME[] = "New salary calculator";

const int  months = 12;
const int PROMPT_COL = 36;
const int HEADING_COL = 19;
const int NAME_SIZE = 40;

char userName[NAME_SIZE]; // IN The User's name
int currentAnnualSalary;  // IN & CALC The annual salary that the user had.
float payIncreaseRate;    // IN & CALC The rate of pay that the user receives.
float newSalary;          // CALC & OUT The user's new salary
float newMonthlySalary;   // CALC & OUT The user's new monthly salary
float retroPay;           // CALC & OUT The user's rectroactive pay


/*******************************************************************************
		 * * OUTPUT - Class Heading
*******************************************************************************/
cout << left;
cout << "**********************************************************\n";
cout << "* PROGRAMMED BY : " << PROGRAMMER << endl;
cout << "* " << setw(14) << CLASS << "CLASS" << ": " << CLASS << endl;
cout << "* " << setw(14) << "SECTION" << ": " << SECTION << endl;
cout << "*ASSIGNMENT #" << setw(9) << ASSIGNMENT_NAME << ": " << endl;
cout << "**********************************************************\n\n";
cout << right;

/*******************************************************************************
 * INPUT - the user will input their name (userName)
 *       - The user will input their current annual salary (currentAnnualSalary)
 *       - The user will input the pay rate increase (payIncreaseRate)
 *       - The user will input their retroactive pay (retroPay)
 ******************************************************************************/
cout <<left <<setw(PROMPT_COL) <<"What is your name?";
cin.getline(userName,NAME_SIZE);
cout << setw(PROMPT_COL);
cout << "What is your current annual salary? ";
cin >> currentAnnualSalary;
cout << setw(PROMPT_COL);
cout << "What is your pay increase rate? ";
cin >> 	payIncreaseRate;
cin.ignore(1000,'\n');
cout << endl;

/*******************************************************************************
* PROCESSING - The program will calculate the following:
* current annual salary
* pay increase rate
* Retroactive pay
*******************************************************************************/
 	newSalary = currentAnnualSalary* payIncreaseRate + currentAnnualSalary;

 	newMonthlySalary = newSalary/months;

 	retroPay = ((currentAnnualSalary*payIncreaseRate)/months)*6;

/*******************************************************************************
* Output -
* This program will output the new salary
* The program will output the newMonthly salary
* In this line we will output the retroactive pay
*******************************************************************************/
cout << userName <<  setw(3) << "\'s" << "SALARY INFORMATION";
cout << endl;
cout << left << "New Salary" << right << setw(HEADING_COL) << "Monthly Salary"
	 << setw(HEADING_COL) << "Retroactive Pay";
cout << endl;
cout << setprecision(2) << fixed
	 << right <<  setw(10) << newSalary << right << setw(19) << newMonthlySalary
	 << setw(19) << retroPay;
cout << setprecision(6);
cout.unsetf(ios::fixed);

	return 0;
}
