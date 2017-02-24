# FRC
#include "WPILib.h"
#include "Spark.h"

class Robot: public IterativeRobot
{
	//Construct for objects here
	Joystick *driveStick;
	Joystick *manipulatorStick;
	CANTalon *lDrive1;
	CANTalon *lDrive2;
	CANTalon *rDrive1;
	CANTalon *rDrive2;
	DoubleSolenoid *Shifter;//
	Spark *spark1;

public:
	Robot() {
		Wait(1);
		driveStick = new Joystick (0);
		manipulatorStick = new Joystick (1);
		lDrive1 = new CANTalon(1);
		lDrive2 = new CANTalon(2);
		rDrive1 = new CANTalon(3);
		rDrive2 = new CANTalon(4);
		Shifter = new DoubleSolenoid (0,1);
		spark1 = new Spark (0);

		//CameraServer::GetInstance()->SetQuality(50);
		//table = NetworkTable::GetTable("GRIP/myContoursReport");
	}

private:
	


	void AutonomousInit() // code for auto mode !!!this will run and stop only when disabled!!!
	{
		// code for auto goes here !!!It will run when auto is enabled on the ds!!!
	}

	void TeleopInit() // holds code for pre teleop enable
	{

	}

	void TeleopPeriodic() // code for the robot to move is placed here (runs when
	// the robot is enabled in teleop mode)
	{
		//CameraServer::GetInstance()->StartAutomaticCapture("cam0");
				//SmartDashboard::PutNumber("DB/Slider 0", accel->GetX());
				//SmartDashboard::PutNumber("DB/Slider 1", accel->GetY());
		//		SmartDashboard::PutNumber("DB/Slider 2", accel->GetZ());
				//SmartDashboard::PutNumber("DB/Slider 3", gyro->GetAngle());
				//frame = imaqCreateImage(IMAQ_IMAGE_RGB, 0);

				//distance = (sonicIn->GetRaw() * inches);
				//sonicOut->Pulse(10);

				if(driveStick->GetRawButton(4))
				{
					spark1->Set(1);
				}
				else
				{
					spark1->Set(0);
				}

				Wait(0.005);
	}// end TeleopPeriodic

	void TestInit()
	{

	}

	void TestPeriodic()
	{

	}

};

START_ROBOT_CLASS(Robot)
